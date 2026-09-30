---
title: Privacy Policy
description: How Bodymap handles your data.
---

# Privacy Policy

**Bodymap — training log**

| | |
| --- | --- |
| **Effective** | `08/09/2026` |
| **Last updated** | `27/09/2026` |
| **Applies to** | the Bodymap mobile app |

---

## The short version

- **You do not need an account.** Bodymap works fully without one, and everything you log stays on your phone.
- **There is no analytics or advertising code in this app.** No Firebase, no ad SDK, no third-party tracker, no profiling, and nothing that follows you across other apps or websites.
- **We never sell or share your data for advertising.** There is no mechanism in the app to do so.
- **Your training log is only uploaded if you have Bodymap Pro** and are signed in. Cloud sync is the feature Pro sells; a free account does not upload the log.
- **Workouts from other apps are opt-in and read-only.** If you connect Health Connect, Bodymap reads the workouts apps like Strava and Garmin Connect saved there — type, time, distance and steps — and nothing else. It never writes to Health Connect. See §6.
- **You can take everything with you at any time.** Profile → Export produces a spreadsheet of every set and a full backup file — including anything the free tier does not display.

---

## Contents

1. [Who we are](#1-who-we-are)
2. [What Bodymap stores](#2-what-Bodymap-stores)
3. [Without an account](#3-without-an-account)
4. [With an account](#4-with-an-account)
5. [Exercises you create](#5-exercises-you-create)
6. [Workouts from other apps (Health Connect)](#6-workouts-from-other-apps-health-connect)
7. [Subscriptions and payments](#7-subscriptions-and-payments)
8. [Who else is involved](#8-who-else-is-involved)
9. [Why we process it](#9-why-we-process-it)
10. [Your rights and controls](#10-your-rights-and-controls)
11. [Deleting your data](#11-deleting-your-data)
12. [Retention and security](#12-retention-and-security)
13. [Children](#13-children)
14. [Changes and contact](#14-changes-and-contact)

---

## 1. Who we are

Bodymap is a training log for phones. It records the sets you lift, shows which muscles you have covered in the last seven days, and tells you what you left out.

The controller of any personal data described here is `Thomas Harris`, `Thailand`. Reach us at `thomasharris0147@gmail.com`.

This policy covers the Bodymap mobile app. It does not cover the app stores you download it from, which have their own policies.

---

## 2. What Bodymap stores

Most of what Bodymap holds never leaves your phone. This table is the whole inventory.

| What | Where | Who can see it |
| --- | --- | --- |
| Your training log — sessions, exercises, sets, reps, weights, cardio | Device · Cloud *(Pro only)* | You. With Pro, also stored in your account so your other devices can read it. |
| Bodyweight weigh-ins | Device · Cloud *(Pro only)* | You. Used for calorie estimates. |
| Your settings — units, split, goal, sessions per week, coverage target, display choices | Device · Cloud *(Pro only)* | You. |
| Sex and year of birth | Device · Cloud *(Pro only)* | You. Both optional and both blank until you fill them in. Used for two things only — see below. |
| Which strength standard your ranks are graded against, and the ranks you have been shown | Device · Cloud *(Pro only)* | You. Derived from the answer above unless you change it. |
| Exercises you create | Device | Only you. |
| Workouts imported from Health Connect — activity type, start time, duration, distance, steps, and the name of the app that recorded them | Device · Cloud *(Pro only)* | You. Only if you connect Health Connect; they become ordinary entries in your training log. See §6. |
| Email address | Cloud | Only if you create an account. Used to sign you in and to contact you about the account. |
| Display name and profile picture | Cloud | Only if you create an account. Supplied by you, or by Google if you sign in with Google. |
| Subscription status — plan, renewal date, store purchase identifiers | Cloud | Only if you buy Bodymap Pro. Never card numbers (see §7). |
| Which app version and platform made a request | Cloud | Ordinary server logs kept by our hosting provider, including your IP address. |

**What Bodymap does not collect at all:** your location or routes, contacts, photos, microphone or camera, device advertising identifiers, your height, your full date of birth, your gender identity, your heart rate, or anything from Apple Health. From Google Health Connect it reads only the three kinds of workout data described in §6, and only if you connect it.

The Android permissions the app requests are: internet access; billing; saving an image to your photo library (Android 9 and below only, when you save a share card); and, only if you choose to connect Health Connect, reading exercise sessions, distance and steps.

Training and bodyweight records say something about your health. We treat them as sensitive, which is why they stay on your device unless you have specifically bought a feature whose entire purpose is to sync them.

### Sex and year of birth

Both are optional. Setup offers them on one screen with a **Skip both** button, and Profile → About you can change or clear either at any time. Left blank, the app behaves exactly as it did before the fields existed.

They feed **two** things and nothing else.

The first is the Schofield equation, used by the WHO and FAO, which estimates how many calories your body spends at rest. Every calorie figure in Bodymap is reported net of that resting figure, so getting it closer to right makes training numbers slightly more honest — a few kcal on a session.

The second is which published strength standard your ranks are compared to, since those standards differ by sex. That comparison is a choice of peer group rather than a fact about you, so it is a separate setting you can change at any time in Profile → About you without touching the sex field — and leaving it alone simply uses the midpoint of the two.

Three deliberate limits on what we ask:

- **Sex, not gender identity.** The equation's coefficients track lean-mass distribution, which is a fact about bodies rather than about identity. A gender field would be the more sensitive question to hold and the app would have no use for the answer — there is no gendered content anywhere in it. "Prefer not to say" is a real option and simply averages the two curves.
- **Year of birth, not date of birth.** The equation works in broad age bands, so the year is all it needs. A full birth date is a much stronger identifier and would buy nothing.
- **No height at all.** The equations that use a height term move a session figure by well under one percent, which does not justify asking.

---

## 3. Without an account

You can use Bodymap without ever signing in — choose **Continue without an account** on the first screen. Nothing about your training is transmitted anywhere.

Your log is written to your phone's own app storage, under keys such as `vessel.state.v1` — the internal prefix keeps the project's original name, because renaming a storage key would orphan an installed app from its own log. It is included in whatever device backup you have configured with Google or Apple, so that reinstalling Bodymap or setting up a new phone can bring your training back; that backup is your own, held in your Google or Apple account under their policies rather than this one, and we cannot read it. On Android the app asks for only the one file its log lives in to be included — not the caches its payment provider keeps.

Uninstalling Bodymap deletes everything it wrote to the phone. Whether a copy remains in your own device backup afterwards is a matter for Google's or Apple's settings, and you can turn that backup off there. Nothing here is a substitute for **Profile → Export**, which is the copy you hold yourself.

Even in this mode the app makes two kinds of outbound request, which are described in §8: fetching its typeface on first launch, and looking up artwork when you create your own exercise.

---

## 4. With an account

Creating an account stores your email address, and a display name and picture if you provide them or sign in with Google. That is the whole profile.

### Free accounts do not sync

Signing in on a free account gives you the shared exercise library and somewhere for a future subscription to live. It does **not** upload your training log, and it does not download one — your device copy is left exactly as it is.

### Pro accounts sync

With Bodymap Pro, your log is mirrored to your account as a single encrypted-in-transit document so your other devices can read it. Your device copy stays the source of truth while the app is running; uploads are batched rather than sent on every tap.

If you sign in on a phone that already has training on it and your account also has a log, Bodymap asks which one to keep rather than silently discarding either.

Signing out removes the copy on that device, so the next person to sign in on it starts from their own account.

---

## 5. Exercises you create

Bodymap ships with a library of exercises, and you can add your own — a movement the library does not cover, or a variation you prefer.

**Exercises you create stay on your device.** They are not uploaded, not published, and not visible to anyone else. There is no way in the app to share one with another user.

More broadly: **nothing you write in Bodymap is ever shown to another user.** Not your exercise names, not your notes, not your sets. The only content that travels between users is the built-in exercise library, which we maintain.

When you create an exercise, the app may look for a matching illustration in an open exercise database — see §8 for exactly what that sends.

---

## 6. Workouts from other apps (Health Connect)

Bodymap can bring in workouts you record in other apps — Strava, Garmin Connect, Runkeeper, MapMyRun and any other app that saves workouts to Google's Health Connect on your phone. This is off until you switch it on in **Settings → Connected apps**, and it only works on the phone you switch it on for.

**What it reads.** With your permission, Bodymap reads three kinds of data from Health Connect:

- **Exercise sessions** — the type of workout (a run, a ride, a swim), when it started and finished, and which app recorded it.
- **Distance** — how far the workout covered, as measured by the app that recorded it.
- **Steps** — steps taken during the workout.

It reads workouts from the period you choose when connecting (from that day, or up to 30 days before) and from then on. It does **not** read routes or location, heart rate, calories, sleep, or any other health data, and it **never writes anything to Health Connect**.

**How it is used.** Each workout becomes a cardio entry in your training log, on the day it happened, so it counts toward your burn, your history and your weekly picture exactly like one you typed in. Strength sessions and workout types Bodymap has no activity for are left out. That is the only use: the data is not used for advertising, is not sold, is not shared with anyone, and is not used to train any model.

**Where it is stored.** Imported workouts are part of your training log, so they are stored the same way — on your device, and in your account only if you have Bodymap Pro and are signed in (§4). Health Connect data is never sent anywhere else.

**Your control.** You can remove any imported workout from your log, and it will not be imported again. **Disconnect** in Settings → Connected apps stops importing and gives back Bodymap's Health Connect access; you can also change or revoke access at any time in Health Connect's own settings. Disconnecting does not delete workouts already imported — delete those individually, or use Clear all data.

Bodymap's use of information received from Health Connect adheres to the [Health Connect Permissions policy](https://support.google.com/googleplay/android-developer/answer/12991134), including its Limited Use requirements.

---

## 7. Subscriptions and payments

**We never see your card details.** Payment is handled entirely by the app store you bought through — Google Play or Apple — who act as merchant of record. No payment information reaches Bodymap or its servers.

Subscription state is managed for us by RevenueCat, which records a purchase identifier, which plan you bought, whether it renews, and when the current period ends. We store the same facts against your account so the app knows to unlock Pro features. Buying before you create an account is supported; the purchase is attached to your account when you sign in.

Cancelling or letting a subscription lapse never deletes anything. You keep every session you logged, on the device and in your account; it simply stops syncing.

---

## 8. Who else is involved

Four services, and each one is here for a specific job.

- **Supabase** — hosts the account system and the database. Data is held in `ap-southeast-1`. Database rules restrict every row to the account that owns it.
- **RevenueCat** — subscription management, as described in §7.
- **Google** — Play Billing for purchases; Google Sign-In, but only if you choose it; and Google Fonts, which the app contacts on first launch to download the typeface it is drawn in. That font request reveals your IP address to Google, and happens whether or not you have an account.
- **wger.de** — an open exercise database. When you create your own exercise, the app may send *that exercise's name* to wger to look for a matching illustration. Nothing else is sent: not your account, not your log, not the sets you did.

There is no analytics provider, no crash reporter, no advertising network and no data broker in this list, because the app contains none.

---

## 9. Why we process it

For anyone covered by UK or EU data protection law, our lawful bases are:

- **Performing our contract with you** — running the account, syncing a Pro log, and unlocking what you paid for.
- **Your consent** — creating an account at all, which is something you choose to do and can use the app without. You can withdraw it by deleting the account.
- **Our legitimate interests** — keeping the service secure and working, and defending against abuse, balanced against your interest in not being over-collected from. This is why there is no analytics.
- **Legal obligation** — retaining what tax and consumer law requires us to retain about a purchase.

---

## 10. Your rights and controls

Depending on where you live you may have the right to access, correct, delete, restrict or object to our use of your data, to receive a portable copy, and not to be discriminated against for exercising any of them. We do not sell personal information or share it for cross-context behavioural advertising, as those terms are used in California law.

### Built into the app

- **Export** — Profile → Export produces a CSV of every set you have logged and a complete JSON backup. It always covers your entire history, including sessions older than the ninety days the free tier displays. No request needed, and it works with no account.
- **Correct** — every session, set and weigh-in can be edited or removed in the app, including back-dated ones. Sex and year of birth can be changed or cleared in Profile → About you.
- **Clear all data** — Profile → Clear all data erases the log on the device and, if you are signed in, the copy in your account, leaving the account itself in place.
- **Delete account** — Profile → Delete account removes the account, your email address and everything logged, immediately. See §11.
- **Stop syncing** — sign out, or cancel Pro. Both leave your device copy intact.

### By request

For anything else — a copy of your account record, or deletion if you can no longer reach the app — write to `thomasharris0147@gmail.com`. We will respond within 30 days. You can also complain to your local data protection authority; in the UK that is the Information Commissioner's Office.

---

## 11. Deleting your data

**No account.** Uninstall the app, or use Clear all data. Nothing of yours exists anywhere else. Workouts in Health Connect belong to the apps that recorded them and are not affected — Bodymap only ever read them.

**With an account, in the app.** **Profile → Delete account** removes the account, your email address, your profile and everything you have logged — on the device and on the server. It is immediate: there is no grace period and nothing is recoverable, which is why the app offers you the export first.

**With an account, without the app.** If you have changed phone or uninstalled it, email `thomasharris0147@gmail.com` from the address on the account. We will confirm and complete it within 30 days. Full instructions are at [Delete your account](delete-account.html).

**Deleting your account does not cancel a Bodymap Pro subscription.** Billing runs through Google Play, which knows nothing about your Bodymap account — cancel it in the Play Store first, or you will keep being charged.

One thing survives deletion, and we would rather say so plainly: records of a purchase are kept as long as tax law requires, typically six to seven years. They are detached from the deleted account and no longer identify you to us.

---

## 12. Retention and security

Data on your device is kept until you remove it or uninstall. Account data is kept while the account exists, and removed within 30 days of deletion apart from the exceptions in §11. Server logs are kept for a short operational period by our hosting provider.

Everything sent to our servers travels over TLS. Access is restricted at the database itself: every row of a training log is readable only by the account that owns it, and subscription records cannot be written by any app client at all — only by the payment provider's verified webhook. Passwords are hashed by the authentication provider and are never visible to us.

No system is perfectly secure, and we would be misleading you to claim otherwise. If a breach affects your data we will notify you and the relevant regulator as the law requires.

If you are outside `ap-southeast-1`, your data will be transferred there and protected by appropriate safeguards, such as the UK and EU standard contractual clauses.

---

## 13. Children

Bodymap is not directed at children and is not intended for anyone under 13, or under 16 where local law sets that age for consent. We do not knowingly collect data from them. If you believe a child has created an account, contact us and we will delete it.

---

## 14. Changes and contact

If this policy changes materially — a new third party, a new category of data, a new purpose — we will update the date at the top and tell you in the app before the change takes effect. Minor clarifications will just be dated.

`Thomas Harris`
`257/158 Hang Dong Ban Waen Chiang Mai Thailand 50230`
`thomasharris0147@gmail.com`

---

*Bodymap — a training log that reads your week and tells you what you left out.*
