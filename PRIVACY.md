# Privacy Policy

**Last updated:** July 4, 2026

This privacy policy applies to **Keychain** ("the app"), available
as an Android application, as a desktop application for Windows, and as
a browser-based web version. The app is offline-first software that runs
entirely on your device. This policy explains what the app does — and,
more importantly, what it does **not** do — with your data. The policy
applies equally to all three versions; where their behavior differs,
the relevant section calls it out explicitly.

---

## Quick summary

- **Your data stays on your device.** The app has no backend server
  and no user account. The only times data leaves the device are
  (1) data exports you save or share manually, and (2) optional
  device-to-device transfers you explicitly initiate over your local
  network. See *Device-to-device transfer* below.
- We **do not collect, transmit, share, or sell** any data about you or
  the data you enter into the app.
- We **do not use** analytics, advertising, crash reporting, telemetry,
  or any tracking SDK.
- **Camera access** (Android) is requested only when you tap "Scan QR"
  inside the Vault tool. On the **desktop** app, which has no camera,
  "Scan QR" instead captures an image of your screen so you can drag a
  box around an on-screen QR code. In both cases the image is processed
  entirely on-device and never transmitted.
- **Internet access** is required as a framework dependency. The app
  itself does not call any servers we operate, because no such servers
  exist. The few situations in which external network traffic can
  occur — Google Play services, optional LAN transfers between your
  own devices, and links you choose to open — are listed in the
  *Permissions → Internet* section below.
- The app offers an **optional tip jar**. Payments are processed by
  Google Play (Android) or by Ko-fi / PayPal (web / desktop). The app
  never receives your payment details.

---

## What information we do not collect

We do not collect, store on any server, transmit, or share:

- Your passwords, authenticator (TOTP) secrets, recovery / backup
  codes, vault entries, bills, the mortgage details you enter into the
  Bill Manager's mortgage estimator, checklists, inventory items,
  addresses, the services tied to those addresses, hashes, encrypted
  strings, or any other content you enter into the app.
- Your name, email address, phone number, postal address, payment
  information, or any other personally identifiable information.
- Your device identifier, advertising identifier, IP address, precise or
  approximate location, network information, or browsing activity. (The
  optional Atlas device-2FA feature reads a stable device identifier
  **on-device only**, to derive a per-device credential — it is processed
  locally, never sent to us, and no server we operate exists to receive it;
  see *Atlas device two-factor authentication* below.)
- Diagnostic, crash, performance, or usage data.
- Camera images, video frames, desktop screen captures, or the contents
  of QR codes you scan.
- The contents of any PDF files you merge or split with the PDF tool —
  they are read and processed entirely on your device and the result is
  written only to the location you choose.

The app has no analytics, no advertising network, no third-party
tracking, and no remote configuration. Nothing about you ever reaches a
server we control because no such server exists.

---

## What is stored on your device

The app stores data locally on your device, in storage areas that are
isolated to the app and not accessible to other apps:

- **Vault entries** (service name, optional username / email, password,
  optional TOTP authenticator secret, optional recovery / backup codes,
  and an optional reference linking the entry to one of your Bill Manager
  entries) are encrypted with **AES-256-GCM** using a key derived from
  your master passphrase via **PBKDF2-SHA-256 with 250,000 iterations**.
  Your master passphrase is never stored.
- **Encrypted inventory checklists** are protected with the same
  algorithms, using a separate passphrase you choose.
- **Bills, hypothetical "what-if" bills (planning entries used by the
  Insights panel), monthly-budget categories (recurring spending
  envelopes used by the Insights projection), income figures
  (including an optional next-pay-day date you may enter), an optional
  current account balance you may enter to drive the Insights balance
  projection, the mortgage details you enter into the Bill Manager's
  mortgage estimator (loan terms, optional escrow / tax / insurance
  figures, and the extra payments and refinances you log — used only for
  on-device projections), saved checklists (regular and recurring types),
  addresses, the services tied to those addresses, baby tracker data
  (an optional baby profile with name, date of birth, optional time of
  birth, notes, and your chosen measurement units for the baby tools;
  the feeding-tool settings; the recorded feedings themselves with their
  timestamps, durations, optional volume, and diaper checks; an
  in-progress feeding-timer state held while a Record session is open;
  and the growth-log entries you add — dated measurements such as weight,
  height, and head circumference, plus any vaccinations, milestones, and
  notes you record), saved trails from the Trail tool (the compass
  headings, step counts, and any notes you record — no location data),
  the TCG card collection (the editions you add and the cards within
  them — set codes, indexes, and any optional names and quantities),
  saved password-generator settings, custom themes you create, your
  reminder-time setting, your active theme, and other UI state** are
  stored in the app's local storage. These
  items are stored without additional encryption beyond the operating
  system's app sandbox.
- **Files you export** (vault, addresses, checklist, etc.) are
  encrypted with a passcode you choose before being written to the
  location you select.
- **The Atlas device-2FA Credential ID** (an opaque per-device value
  derived locally — see *Atlas device two-factor authentication* below)
  is cached in local storage. The Atlas 2FA secrets you enroll are saved
  as ordinary vault entries, encrypted like everything else in the vault.

You can remove this data at any time by uninstalling the app or by
clearing app storage from your device's Settings → Apps screen.

---

## The web version

Keychain is also offered as a **browser-based web version** — for
example, the playable embed on its itch.io page — so you can try it
without installing anything. It is the same application, delivered as
static files that run entirely in your browser. There is no account, no
backend, and no server we operate.

- **Your data stays in your browser.** Everything you enter is saved in
  your browser's local storage on your own device, exactly as the apps
  store theirs. Your vault and any encrypted inventories remain
  encrypted with **AES-256-GCM** using a key derived from your
  passphrase. Nothing you enter is uploaded.
- **What the host can see.** Because the page itself is downloaded from
  a host (the itch.io content-delivery network, or another static host),
  that host receives the ordinary request information every website
  does — your IP address, browser user-agent, and which files were
  requested — for the sole purpose of serving the page. It never
  receives the data you enter into the app, which never leaves your
  browser. We do not add analytics, advertising, or tracking scripts.
- **Some features need the apps.** The web version is intended as a way
  to try Keychain. Capabilities that require the operating system —
  encrypted device-to-device transfer and Sync, local backups to a
  folder, and scheduled bill reminders — are available only in the
  Android and Windows desktop apps. You can export your data from the
  web version and import it into either app.
- **Storage is per-browser.** Data saved in the web version lives in
  that specific browser on that device, and clearing the browser's site
  data removes it. Use the export feature to keep a copy or to move your
  data into one of the apps.

---

## Permissions

The app declares the following Android permissions:

### Camera (`android.permission.CAMERA`)

Requested at runtime, the first time you tap "Scan QR" inside the Vault
tool. Used solely to scan QR codes that contain `otpauth://` URIs for
configuring Time-based One-Time Password (TOTP) two-factor
authentication. The camera viewfinder is presented by Google ML Kit,
which decodes the QR code on your device. The decoded text is then
written to the Authenticator key field where you can review and save it.

The camera image is never saved to disk, never transmitted off the
device, and is not used for any purpose other than the QR-code scan you
explicitly initiated. You can deny or revoke this permission at any time
in your device settings; the rest of the app continues to work normally
without it.

### Screen capture (desktop only)

The Windows desktop app has no camera, so when you tap "Scan QR" inside
the Vault tool it captures an image of your connected monitor(s) and
shows it to you so you can drag a box around an on-screen QR code. The
capture is decoded entirely on-device by a bundled QR-reader library
(jsQR) and is held only in memory for the duration of the scan: it is
never saved to disk, never transmitted off the device, and is discarded
as soon as the scan finishes or you close the scanner. This applies only
to the desktop build; the Android app uses the camera described above
and never captures the screen.

### Internet (`android.permission.INTERNET`)

Declared because it is required by the Capacitor framework that hosts
the app on Android. The app itself does not contact any servers we
operate, because no such servers exist. External network traffic can
occur in the following situations, all of them either user-initiated
or routed entirely through Google Play services:

- **ML Kit barcode-scanning model download** — a one-time, on-demand
  download requested by Google Play Services the first time you use
  the QR scanner. Once the model is on your device, scanning runs
  fully offline.
- **Google Play Billing** — when you choose to tip from inside the
  app on Android, the purchase flow is owned end-to-end by the Google
  Play Billing service. The app receives only a confirmation that a
  tier was purchased.
- **Google Play in-app updates** — the app checks the on-device Play
  Store for app updates and may surface a prompt. This check is
  brokered by Google Play services on your device; we don't operate
  a separate update server.
- **Device-to-device LAN transfer** — when you explicitly start a
  transfer (see *Device-to-device transfer* below), the two devices
  exchange data peer-to-peer on your local network. Nothing leaves
  the LAN.
- **External links you choose to open** — for example, a bill's
  billing-portal URL, a tracked-service URL in Addresses, or the
  Ko-fi / PayPal links in the Support panel. Tapping such a link
  hands control to your default browser; we don't see or record what
  you do there.

No other network calls are made. The desktop (Tauri / Windows) build
behaves the same way: no servers operated by us, the same five
situations above, with Google Play services replaced by the Microsoft
Store mechanisms where relevant.

### Notifications (`android.permission.POST_NOTIFICATIONS`)

Used to post local notifications on your device: scheduled **bill
reminders**, and — only if you enable it — the **lock-screen feeding
controls** described below. On Android 13 and later the system asks for
this permission at runtime, the first time you turn on a feature that
needs it. Every notification is composed and shown entirely on your
device; nothing about them is collected or transmitted. You can deny or
revoke the permission at any time in your device settings.

### Foreground service (`android.permission.FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_SPECIAL_USE`)

Declared solely to power the optional **lock-screen feeding controls**.
When you turn this on (Settings → General → *Lock-screen & background
controls*, off by default) and start recording a feeding, the app runs a
foreground service that shows an ongoing notification with **Pause**,
**Switch side**, and **End** buttons and a live timer, so you can control
the feeding without unlocking your phone. The service runs **only while a
feeding is actively being recorded** and is removed as soon as you end or
discard the feed, or disable the feature. It performs no networking,
collects nothing, and transmits nothing — all timing stays on your
device. The feeding data itself is stored exactly as described above
regardless of whether this feature is on.

### Motion & orientation sensors (no permission required)

The **Trail** tool reads your device's orientation/compass sensor (via
the standard web DeviceOrientation API) to show your current heading
while you record a path. No Android permission is required for this, and
no location/GPS is used. The readings are used live on your device; only
the headings you choose to save as trail legs are stored locally (see
*What is stored on your device*). Nothing from these sensors is collected
or transmitted.

### Physical activity (`android.permission.ACTIVITY_RECOGNITION`)

Used **only** for the Trail tool's optional **automatic step counting**.
When you turn it on (Trail settings, or Settings → General →
*Lock-screen & background controls*, off by default) and record a trail,
the app reads the device's hardware **step counter** so it can fill in
distance without you typing step counts — including while the screen is
off, via an ongoing notification posted by a foreground service. It runs
**only while a trail is actively recording** and stops when you finish,
discard, or disable the feature. Only the resulting step counts per leg
are stored locally; the permission is requested at runtime, used entirely
on-device, never collected or transmitted, and revocable any time in your
device settings.

---

## Third-party services

The app integrates with the following third-party components, all of
them on-device or invoked only at your explicit request:

- **Google ML Kit Barcode Scanning** (provided by Google Play Services
  on Android). Used exclusively to decode QR codes captured by the
  camera. Scanning happens on-device after the one-time model
  download. See Google's privacy policy at
  <https://policies.google.com/privacy>.
- **Google Play Billing** (Android only, invoked only when you choose
  to tip). Handles the entire purchase flow. The app sees only the
  product ID and a transaction confirmation; it does not see your
  payment details. See Google's policy linked above.
- **Google Play In-App Update API** (Android only). Used to detect
  whether a newer version of the app is available in the Play Store
  and to surface the standard update prompt. The check is brokered by
  the on-device Play Services; we don't run a separate update server.
- **Ko-fi and PayPal** (web / desktop only, invoked only when you
  choose to tip). The Support panel opens an external link to these
  services in your default browser. Once you leave the app, your
  interaction is governed by their respective privacy policies
  (<https://ko-fi.com> and <https://www.paypal.com>). The app does
  not record whether you completed a donation.

The app does not include or integrate with any third-party analytics,
advertising, crash-reporting, attribution, or tracking service.

---

## Donations and in-app purchases

The app offers an optional tip jar so you can support development.
We do not process any payment ourselves and we never see your payment
details.

### On Android (Google Play Billing)

If you choose to tip from inside the app, the purchase is handled by
Google Play. The app only receives a confirmation that a tier was
purchased — it never receives your name, card number, billing address,
or any other payment information. Payments are governed by Google's
terms and privacy policy at <https://policies.google.com/privacy>.

The app stores two values locally to drive the "Lifetime tips" counter
shown in the Support panel:

- The number of tips you have given.
- The timestamp of the most recent tip.

Both are stored only on your device. They are never transmitted.

### On web / desktop (Ko-fi or PayPal)

On platforms without in-app billing, the Support panel offers external
links to Ko-fi (<https://ko-fi.com>) and PayPal
(<https://www.paypal.com>) which handle donations directly. Tapping
either button opens the chosen service in your default browser. Once
you leave the app, your interaction is governed by that service's
privacy policy. The app does not record whether you completed a
donation.

---

## Device-to-device transfer (LAN)

Several tools and a Settings entry offer an optional transfer feature
that lets you move data between two of your own devices directly over
your local network — for example, between your phone and your desktop
computer, or directly between two phones. Supported sources are the **Vault**, **Bills** (including
**what-if bills**), **Addresses**, **Checklist**, **TCG** (card editions
and the cards within them), **Custom Themes**, **Newborn Feeding**
(baby profile, feeding settings, and feeding entries), and **Growth**
(the baby's growth-log entries) tools, plus a
**Settings → Transfer** composer that bundles a selection
from any combination of those tools — and the Bill Manager's mortgage
estimate — into a single transfer. This feature
only runs when you explicitly start a transfer; it never runs in the
background.

When you transfer data:

- The two devices exchange data peer-to-peer over Wi-Fi. The data
  never reaches a server we operate — no Keychain backend exists.
- The payload is encrypted with **AES-256-GCM** before it leaves the
  sending device. The encryption key is derived on both ends from a
  32-byte random value shown only inside the QR code, so a network
  observer without the QR has nothing usable to read.
- A 4-digit verification code is shown on both screens. You confirm
  the two codes match before any data moves — that catches the case
  where you scanned the wrong QR.
- The transfer server runs for at most five minutes and only accepts a
  single successful transfer before shutting itself down. Three failed
  authentication attempts also shut it down. Nothing about the session
  is written to disk — the encryption key, token, and port are held
  in memory only.

If you transfer data to a device you don't own (for example, sending
an export to a family member), once it lands on the other device it
is governed by whatever happens on that device. You are responsible
for choosing who you transfer to.

---

## Atlas device two-factor authentication (optional)

Keychain can act as an authenticator for **Atlas**, a separate
application you may use. This feature is entirely optional and only does
anything when you choose to enroll a device.

When you enroll, Keychain needs a **Credential ID** that stays the same
for this device — including across an app reinstall — because Atlas
identifies your devices by it. To produce one without it changing, the
app reads a **stable device identifier** and derives the Credential ID
from it:

- On **Windows desktop**, the operating system's `MachineGuid`.
- On **Android**, the system `ANDROID_ID`, read through the
  `@capacitor/device` plugin.

This identifier is **processed entirely on your device**: it is combined
with a fixed app-specific value and passed through a one-way **SHA-256**
hash, and only the resulting opaque `KC-…` Credential ID is kept. The raw
device identifier is never stored and never transmitted, and — as with
everything else in the app — there is no server we operate for it to be
sent to. On platforms with no such identifier (the web build) a random
value is generated and stored locally instead.

Enrolling also generates a fresh TOTP secret, which is saved as a normal
(encrypted) entry in your vault so the rolling 6-digit code appears in
your authenticator list. Keychain assembles the Credential ID, the
secret, and the device name you type into a single registration token
(shown as text and a QR code). **You** copy that token into your own
Atlas instance — Keychain itself makes no network connection to Atlas.
From that point the Credential ID and secret are governed by your Atlas
setup; how Atlas uses them is covered by Atlas's own policies.

---

## Data exports and external links

If you use the app's export feature to save a backup of your vault,
checklists, bills, addresses, or baby tracker data — or the **PDF
tool** to merge or split PDFs — the resulting file is created on your
device at the location you choose (typically your Downloads folder, the
Import/Export folder you configured, or another location you select via
the system file picker). The PDF tool reads the source PDFs you pick and
performs the merge or split entirely on-device using bundled libraries
that make no network calls; the input files are not retained by the app
and the output is written only where you direct it. Once exported, you
are solely responsible for that file. We strongly recommend you only
export to locations you control and only share the files with parties
you trust.

The **Local backup** feature (Settings → Transfer) writes a single
file containing everything on the device — all of the collections
listed above plus your settings and preferences — to the same
local folder. Your vault entries and any encrypted inventory
checklists stay encrypted inside that file; the remaining sections
(bills, plaintext checklists, addresses, custom themes, preferences)
are written as-is, without additional encryption. Like any export it
is created locally, only when you ask for it, and never transmitted
anywhere — treat the backup file as sensitive and keep it somewhere
you control. Restoring a backup reads such a file you select and
merges it into the current device.

The Bill Manager and Addresses tools can open external URLs you have
entered (for example, a billing portal, or the page you use to
update an address with a given service). Tapping such a link launches
your default browser, which is governed by its own privacy policy. We
do not see or record which links you open.

---

## Children's privacy

The app does not knowingly collect any data from anyone, including
children under the age of 13. Because the app does not collect data at
all, no special handling for children's data is required.

---

## Your rights

Because the app stores all data locally on your device, you already
have full control over it:

- **Access:** all of your data is visible inside the app.
- **Correction:** you can edit any entry directly.
- **Deletion:** you can delete any entry directly, or remove all app
  data by clearing app storage or uninstalling the app.
- **Portability:** you can export your data at any time using the
  built-in export features.

We do not need to provide a request mechanism for these rights because
no data leaves your device for us to act on.

---

## Changes to this policy

If this policy changes in a material way, we will update the "Last
updated" date at the top and, where appropriate, note the change in the
app's release notes.

---

## Contact

For questions about this policy or the app, contact:

**Email:** _louis.g.mareau@gmail.com_

---
