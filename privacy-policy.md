---
title: Privacy Policy
description: How Bodymap handles your data.
---

# Privacy Policy

**Bodymap — training log**

| | |
| --- | --- |
| **Effective** | `08/09/2026` |
| **Last updated** | `08/09/2026` |
| **Applies to** | the Bodymap mobile app |

---

## The short version

- **You do not need an account.** Bodymap works fully without one, and everything you log stays on your phone.
- **There is no analytics or advertising code in this app.** No Firebase, no ad SDK, no third-party tracker, no profiling, and nothing that follows you across other apps or websites.
- **We never sell or share your data for advertising.** There is no mechanism in the app to do so.
- **Your training log is only uploaded if you have Bodymap Pro** and are signed in. Cloud sync is the feature Pro sells; a free account does not upload the log.
- **You can take everything with you at any time.** Profile → Export produces a spreadsheet of every set and a full backup file — including anything the free tier does not display.

---

## Contents

1. [Who we are](#1-who-we-are)
2. [What Bodymap stores](#2-what-Bodymap-stores)
3. [Without an account](#3-without-an-account)
4. [With an account](#4-with-an-account)
5. [Exercises you publish](#5-exercises-you-publish)
6. [Subscriptions and payments](#6-subscriptions-and-payments)
7. [Who else is involved](#7-who-else-is-involved)
8. [Why we process it](#8-why-we-process-it)
9. [Your rights and controls](#9-your-rights-and-controls)
10. [Deleting your data](#10-deleting-your-data)
11. [Retention and security](#11-retention-and-security)
12. [Children](#12-children)
13. [Changes and contact](#13-changes-and-contact)

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
| Exercises you create | Device | Only you — unless you choose to publish one (see §5). |
| Email address | Cloud | Only if you create an account. Used to sign you in and to contact you about the account. |
| Display name and profile picture | Cloud | Only if you create an account. Supplied by you, or by Google if you sign in with Google. |
| Subscription status — plan, renewal date, store purchase identifiers | Cloud | Only if you buy Bodymap Pro. Never card numbers (see §6). |
| Which app version and platform made a request | Cloud | Ordinary server logs kept by our hosting provider, including your IP address. |

**What Bodymap does not collect at all:** your location, contacts, photos, microphone or camera, device advertising identifiers, your activity in other apps, or anything from Apple Health or Google Health Connect. The app requests exactly two Android permissions — internet access, and billing.

Training and bodyweight records say something about your health. We treat them as sensitive, which is why they stay on your device unless you have specifically bought a feature whose entire purpose is to sync them.

---

## 3. Without an account

You can use Bodymap without ever signing in — choose **Continue without an account** on the first screen. Nothing about your training is transmitted anywhere.

Your log is written to your phone's own app storage, under keys such as `Bodymap.state.v1`. It is included in whatever device backup you have configured with Google or Apple; that backup is governed by their policies, not this one. Uninstalling Bodymap deletes it.

Even in this mode the app makes two kinds of outbound request, which are described in §7: fetching its typeface on first launch, and looking up artwork when you create your own exercise.

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

## 5. Exercises you publish

Exercises you create are private to your device by default. If you choose **Share**, that exercise — its name, equipment, muscle groups and default weight — is added to a library every Bodymap user can browse, and is recorded as having been created by your account.

Treat that as public and permanent. Removing it from your own list does not withdraw the shared copy, because other people's logged sessions may already reference it. Do not put anything personal in an exercise name you intend to share. If you need a published exercise taken down, write to us.

Your training log is never shared this way. Publishing an exercise shares the *definition*, never the sets you did.

---

## 6. Subscriptions and payments

**We never see your card details.** Payment is handled entirely by the app store you bought through — Google Play or Apple — who act as merchant of record. No payment information reaches Bodymap or its servers.

Subscription state is managed for us by RevenueCat, which records a purchase identifier, which plan you bought, whether it renews, and when the current period ends. We store the same facts against your account so the app knows to unlock Pro features. Buying before you create an account is supported; the purchase is attached to your account when you sign in.

Cancelling or letting a subscription lapse never deletes anything. You keep every session you logged, on the device and in your account; it simply stops syncing.

---

## 7. Who else is involved

Four services, and each one is here for a specific job.

- **Supabase** — hosts the account system and the database. Data is held in `ap-southeast-1`. Database rules restrict every row to the account that owns it.
- **RevenueCat** — subscription management, as described in §6.
- **Google** — Play Billing for purchases; Google Sign-In, but only if you choose it; and Google Fonts, which the app contacts on first launch to download the typeface it is drawn in. That font request reveals your IP address to Google, and happens whether or not you have an account.
- **wger.de** — an open exercise database. When you create your own exercise, the app may send *that exercise's name* to wger to look for a matching illustration. Nothing else is sent: not your account, not your log, not the sets you did.

There is no analytics provider, no crash reporter, no advertising network and no data broker in this list, because the app contains none.

---

## 8. Why we process it

For anyone covered by UK or EU data protection law, our lawful bases are:

- **Performing our contract with you** — running the account, syncing a Pro log, and unlocking what you paid for.
- **Your consent** — publishing an exercise to the shared library, and creating an account at all, both of which are things you choose to do. You can withdraw consent by deleting the account or asking us to remove a published exercise.
- **Our legitimate interests** — keeping the service secure and working, and defending against abuse, balanced against your interest in not being over-collected from. This is why there is no analytics.
- **Legal obligation** — retaining what tax and consumer law requires us to retain about a purchase.

---

## 9. Your rights and controls

Depending on where you live you may have the right to access, correct, delete, restrict or object to our use of your data, to receive a portable copy, and not to be discriminated against for exercising any of them. We do not sell personal information or share it for cross-context behavioural advertising, as those terms are used in California law.

### Built into the app

- **Export** — Profile → Export produces a CSV of every set you have logged and a complete JSON backup. It always covers your entire history, including sessions older than the ninety days the free tier displays. No request needed, and it works with no account.
- **Correct** — every session, set and weigh-in can be edited or removed in the app, including back-dated ones.
- **Clear all data** — Profile → Clear all data erases the log on the device and, if you are signed in, the copy in your account.
- **Stop syncing** — sign out, or cancel Pro. Both leave your device copy intact.

### By request

For anything else — a copy of your account record, deletion of the account itself, or removal of a published exercise — write to `thomasharris0147@gmail.com`. We will respond within 30 days. You can also complain to your local data protection authority; in the UK that is the Information Commissioner's Office.

---

## 10. Deleting your data

**No account.** Uninstall the app, or use Clear all data. Nothing of yours exists anywhere else.

**With an account.** Clear all data removes your log from both the device and your account. To delete the *account* — your email address, profile and subscription record — email `thomasharris0147@gmail.com` from the address on the account. We will confirm and complete it within 30 days.

Two things survive deletion, and we would rather say so plainly. Exercises you published to the shared library stay, because other people's logged sessions reference them, though we will detach them from your account on request. And records of a purchase are kept as long as tax law requires, which is typically six to seven years.

---

## 11. Retention and security

Data on your device is kept until you remove it or uninstall. Account data is kept while the account exists, and removed within 30 days of deletion apart from the exceptions in §10. Server logs are kept for a short operational period by our hosting provider.

Everything sent to our servers travels over TLS. Access is restricted at the database itself: every row of a training log is readable only by the account that owns it, and subscription records cannot be written by any app client at all — only by the payment provider's verified webhook. Passwords are hashed by the authentication provider and are never visible to us.

No system is perfectly secure, and we would be misleading you to claim otherwise. If a breach affects your data we will notify you and the relevant regulator as the law requires.

If you are outside `ap-southeast-1`, your data will be transferred there and protected by appropriate safeguards, such as the UK and EU standard contractual clauses.

---

## 12. Children

Bodymap is not directed at children and is not intended for anyone under 13, or under 16 where local law sets that age for consent. We do not knowingly collect data from them. If you believe a child has created an account, contact us and we will delete it.

---

## 13. Changes and contact

If this policy changes materially — a new third party, a new category of data, a new purpose — we will update the date at the top and tell you in the app before the change takes effect. Minor clarifications will just be dated.

`Thomas Harris`
`257/158 Hang Dong Ban Waen Chiang Mai Thailand 50230`
`thomasharris0147@gmail.com`

---

*Bodymap — a training log that reads your week and tells you what you left out.*
