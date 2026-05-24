# Privacy Policy

**Last updated:** May 23, 2026

This privacy policy applies to **Keychain** ("the app"), available
as an Android application and as a desktop application for Windows.
The app is offline-first software that runs entirely on your device.
This policy explains what the app does — and, more importantly, what
it does **not** do — with your data. The policy applies equally to
both the Android and desktop versions; where their behavior differs,
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
- **Camera access** is requested only when you tap "Scan QR" inside the
  Vault tool. Camera images are processed on-device and never transmitted.
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
  codes, vault entries, bills, checklists, inventory items, addresses,
  the services tied to those addresses, hashes, encrypted strings, or
  any other content you enter into the app.
- Your name, email address, phone number, postal address, payment
  information, or any other personally identifiable information.
- Your device identifier, advertising identifier, IP address, precise or
  approximate location, network information, or browsing activity.
- Diagnostic, crash, performance, or usage data.
- Camera images, video frames, or the contents of QR codes you scan.

The app has no analytics, no advertising network, no third-party
tracking, and no remote configuration. Nothing about you ever reaches a
server we control because no such server exists.

---

## What is stored on your device

The app stores data locally on your device, in storage areas that are
isolated to the app and not accessible to other apps:

- **Vault entries** (service name, optional username / email, password,
  optional TOTP authenticator secret, optional recovery / backup codes)
  are encrypted with **AES-256-GCM** using a key derived from your
  master passphrase via **PBKDF2-SHA-256 with 250,000 iterations**.
  Your master passphrase is never stored.
- **Encrypted inventory checklists** are protected with the same
  algorithms, using a separate passphrase you choose.
- **Bills, hypothetical "what-if" bills (planning entries used by the
  Insights panel), income figures (including an optional next-pay-day
  date you may enter), an optional current account balance you may
  enter to drive the Insights balance projection, saved
  checklists (regular and recurring types), addresses, the services
  tied to those addresses, saved password-generator settings, custom
  themes you create, your reminder-time setting, your active theme,
  and other UI state** are stored in the app's local storage. These
  items are stored without additional encryption beyond the operating
  system's app sandbox.
- **Files you export** (vault, addresses, checklist, etc.) are
  encrypted with a passcode you choose before being written to the
  location you select.

You can remove this data at any time by uninstalling the app or by
clearing app storage from your device's Settings → Apps screen.

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
computer. Supported sources are the **Vault**, **Bills** (including
**what-if bills**), **Addresses**, **Checklist**, and **Custom Themes**
tools, plus a **Settings → Transfer** composer that bundles a selection
from any combination of those tools into a single transfer. This feature
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

## Data exports and external links

If you use the app's export feature to save a backup of your vault,
checklists, bills, or addresses, the resulting file is created on
your device at the location you choose (typically your Downloads
folder or another location you select via the system file picker).
Once exported, you are solely responsible for that file. We strongly
recommend you only export to locations you control and only share the
files with parties you trust.

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
