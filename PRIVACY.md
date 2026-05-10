# Privacy Policy

**Last updated:** May 10, 2026

This privacy policy applies to the **Keychain** mobile application
("the app") for Android. The app is offline-first software that runs
entirely on your device. This policy explains what the app does — and,
more importantly, what it does **not** do — with your data.

---

## Quick summary

- **All your data stays on your device.** The app has no backend server
  and no user account.
- We **do not collect, transmit, share, or sell** any data about you or
  the data you enter into the app.
- We **do not use** analytics, advertising, crash reporting, telemetry,
  or any tracking SDK.
- **Camera access** is requested only when you tap "Scan QR" inside the
  Vault tool. Camera images are processed on-device and never transmitted.
- **Internet access** is declared as a framework requirement. The only
  external network activity that can occur is an on-demand download of
  Google's barcode-scanning module the first time you use QR scanning.

---

## What information we do not collect

We do not collect, store on any server, transmit, or share:

- Your passwords, authenticator (TOTP) secrets, vault entries, bills,
  checklists, inventory items, hashes, encrypted strings, or any other
  content you enter into the app.
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

- **Vault entries** (passwords, usernames, optional TOTP authenticator
  secrets) are encrypted with **AES-256-GCM** using a key derived from
  your master passphrase via **PBKDF2-SHA-256 with 250,000 iterations**.
  Your master passphrase is never stored.
- **Encrypted inventory checklists** are protected with the same
  algorithms, using a separate passphrase you choose.
- **Bills, regular checklists, saved password-generator settings, theme
  preference, and other UI state** are stored in the app's local
  storage. These items are stored without additional encryption beyond
  the operating system's app sandbox.
- **Files you export** (vault backup, checklist backup, etc.) are
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
the app. The app itself does not contact any servers it controls.

The only external network traffic that can be initiated as a side effect
of using the app is a one-time on-demand download of Google's ML Kit
barcode-scanning model, which happens the first time you use the QR
scanner. This download is requested by Google Play Services on your
device, which is responsible for delivering it. Once the model is on
your device, all QR scanning runs fully offline.

---

## Third-party services

The only third-party component the app integrates with on-device is:

- **Google ML Kit Barcode Scanning** (provided by Google Play Services).
  Used exclusively to decode QR codes captured by the camera. Scanning
  happens on-device. See Google's privacy policy at
  <https://policies.google.com/privacy>.

The app does not include or integrate with any third-party analytics,
advertising, crash-reporting, attribution, or tracking service.

---

## Data exports and external links

If you use the app's export feature to save a backup of your vault,
checklists, or bills, the resulting file is created on your device at
the location you choose (typically your Downloads folder or another
location you select via the system file picker). Once exported, you are
solely responsible for that file. We strongly recommend you only export
to locations you control and only share the files with parties you
trust.

The Bill Manager tool can open external URLs you have entered (for
example, a billing portal). Tapping such a link launches your default
browser, which is governed by its own privacy policy. We do not see or
record which links you open.

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
