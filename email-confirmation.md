# The confirmation and password-reset emails

## The problem this solves

Signing up sends a confirmation email. Tapping the link in it used to open a
browser on a **blank page** — no message, no way to know whether the account
had been confirmed, nothing to tap.

The account *was* confirmed. What failed was the last hop.

Supabase's `/auth/v1/verify` endpoint verifies the token and then redirects the
browser to whatever `emailRedirectTo` asked for. That was
`com.vessel.vessel://login-callback/` — the app's own scheme. Two things go
wrong with that:

- **The mail app's browser cannot follow it.** Gmail and most mail clients open
  links in an embedded browser, which has no handler registered for an unknown
  scheme. The navigation fails silently and the tab is left on `about:blank`.
- **A server-side redirect carries no user gesture.** Even in full Chrome, a
  302 into an external scheme is frequently dropped for exactly that reason.

Either way: blank page, confirmed account, confused user.

The fix is to land somewhere that can always be rendered — a real `https` page —
which then hands the auth parameters to the app behind a genuine tap.

## What was added

`docs/confirm.html` — one self-contained file. No fonts, scripts or images are
fetched; the logo is inlined. It:

1. Reads the parameters Supabase appended to the URL.
2. Shows **Email confirmed** (or **Ready for a new password** for a reset),
   with an **Open MuscleMap** button.
3. Forwards `?code=…` to `com.vessel.vessel://login-callback/` so the app can
   finish signing the user in. On Android it uses the `intent:` form, which
   names the package and falls back to this page when the app is not installed.
4. Shows a real message for an expired or already-used link, with what to do
   next, instead of a blank page.

Nothing is verified and no secret is held on that page. The app uses the PKCE
flow, so the code verifier lives on the device that started the sign-up — the
exchange can only ever happen inside the app. The page carries the code the
last few metres and nothing more.

## The one thing that is easy to miss

The page is only reached if the app **tells Supabase to redirect to it**. That
is `EMAIL_REDIRECT_URL`, and it is a build flag — not a dashboard setting, and
not something the page can arrange for itself.

Leave it unset and `SupabaseConfig.emailRedirect` falls back to
`com.vessel.vessel://login-callback/`, which is the blank page all over again,
with a perfectly good landing page sitting unused in the repo. If you are
looking at a blank tab, check `dart_defines.json` for that key before anything
else.

## Where the file lives, and where it is served from

**This repo serves nothing.** The published site is a separate folder, kept
outside this project, and `docs/confirm.html` is the *source* that gets copied
into it. Editing the file here changes nothing on the web until that copy is
made and pushed.

That means three copies, and the drift between them is the thing most likely to
waste an afternoon:

| Copy | What it is for |
| --- | --- |
| `docs/confirm.html` | the source. Edit this one. |
| `web/confirm.html` | what `flutter build web` picks up. Byte-identical. |
| *your site folder* | what the emails actually reach. |

```bash
cp docs/confirm.html web/confirm.html && cmp docs/confirm.html web/confirm.html
# then copy docs/confirm.html into the site folder and push that
```

If the live page does not match this file, the site folder is stale — that is
the first thing to check, ahead of anything in Supabase.

## Setting it up

### 1. Host the page

It is a static file with no build step and no front matter, so any static host
takes it as-is:

- **GitHub Pages** — copy it into whichever folder the Pages site is built
  from, alongside the privacy policy and the account-deletion page that Play
  requires. The URL is then `https://<user>.github.io/<repo>/confirm.html`, or
  whatever your custom domain is.
- **Netlify / Vercel / Cloudflare Pages** — drag the file in.
- **Your own domain** — copy it next to your other static files.
- **The Flutter web build** — `flutter build web` copies `web/confirm.html` to
  `build/web/confirm.html` untouched.

Whatever you pick, the URL you end up with is what steps 2 and 3 both need.

### 2. Allow the URL in Supabase

**Authentication → URL Configuration → Redirect URLs**, add the exact URL:

```
https://your.domain/confirm.html
```

Leave `com.vessel.vessel://login-callback/` on the list — Google sign-in still
returns to it, and it is the fallback when no page is configured.

### 3. Point the app at it

This project keeps its defines in `dart_defines.json`, so the flag belongs
there beside the others:

```json
{
  "SUPABASE_URL": "https://<project-ref>.supabase.co",
  "SUPABASE_PUBLISHABLE_KEY": "sb_publishable_...",
  "REVENUECAT_ANDROID_KEY": "goog_...",
  "EMAIL_REDIRECT_URL": "https://<user>.github.io/<repo>/confirm.html"
}
```

```bash
flutter build apk --dart-define-from-file=dart_defines.json
```

Or as a flag, if you are not using the file:

```
flutter build apk \
  --dart-define=SUPABASE_URL=https://<project-ref>.supabase.co \
  --dart-define=SUPABASE_PUBLISHABLE_KEY=sb_publishable_... \
  --dart-define=EMAIL_REDIRECT_URL=https://your.domain/confirm.html
```

`EMAIL_REDIRECT_URL` is read by `SupabaseConfig.emailRedirect` and used for
sign-up confirmation and password-reset emails. Google sign-in is untouched and
keeps using the custom scheme.

**Leaving it unset is safe.** The links fall back to the custom scheme and
behave exactly as they did before — so a build without it is no worse off, it
just does not get the landing page.

## What the app does at its end

The **Check your inbox** screen was rebuilt at the same time, because the
browser was only half the problem:

- The **address the link was sent to** is shown back in a framed row. A typo in
  an email address is the commonest reason nothing ever arrives, and it is
  invisible unless it is put in front of someone.
- **Numbered steps** say what is left to do, in order.
- **Send it again** re-sends the confirmation, behind a 45-second countdown.
  Supabase rate-limits its mailer, and the obvious recovery — going back and
  signing up a second time — fails with "already registered", which reads as a
  dead end to someone whose first email simply never turned up.
- **I have confirmed — sign me in** goes straight back to the sign-in form,
  which is what the user needs when the deep link did not fire.

## Testing it

1. Sign up with a real address in a build carrying `EMAIL_REDIRECT_URL`.
2. Open the email **on the phone** and tap the link.
3. You should see the MuscleMap confirmation page, then the app opening.
4. Tap the same link a second time: the page should say the link has expired or
   been used, and tell you to sign in.

To see the page's states without sending any mail, serve it locally —
`python -m http.server` inside `docs/` — and open it with the parameters by
hand:

```
/confirm.html?code=test123                     -> "Link verified" (type unknown)
/confirm.html?code=test123&type=signup         -> "Email confirmed"
/confirm.html?code=test123&type=recovery       -> "Ready for a new password"
/confirm.html?error=access_denied&error_code=otp_expired&error_description=Email+link+is+invalid+or+has+expired
/confirm.html?error=access_denied&error_code=otp_expired&type=recovery
/confirm.html                                  -> "Nothing to confirm here"
```

The deep link itself will not resolve in a desktop browser — that part only
works on the phone — but every piece of copy, and which section is shown, is
visible.

Supabase does not always say which flow a link came from: a PKCE redirect can
arrive as nothing but `?code=`. That is why there is a third wording, used when
`type` is absent, that is true of a confirmation and a reset alike. Do not
"fix" it into claiming the account was confirmed.

## If you would rather not host anything

Leave `EMAIL_REDIRECT_URL` unset and turn **Confirm email** off in
**Authentication → Providers → Email**. Sign-up then returns a session straight
away and no link is ever sent — the app already handles that path
(`SignUpOutcome.signedIn`). It is a real trade-off: nothing then proves the
address is the user's, and password reset stops working, since that flow has no
version that avoids email.
