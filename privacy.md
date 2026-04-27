# TDInput — Privacy Policy

**Effective Date:** March 19, 2026
**Last Updated:** March 19, 2026

---

## Overview

TDInput is designed with privacy as a core principle. The app processes sensor data entirely on your devices and your local network. No data is collected, stored, uploaded, or shared with anyone — including us.

---

## Data Processing

TDInput reads the following sensor data from your iPhone and Apple Watch:

- Motion and orientation (accelerometer, gyroscope)
- Magnetometer (compass heading)
- Barometric altitude and pressure
- Heart rate and health metrics (via HealthKit, Apple Watch only)
- Digital Crown input (Apple Watch only)
- Battery level

**All sensor data is:**
- Processed in real time on your device
- Transmitted only over your local Wi-Fi network to a destination IP address you configure (your Mac running TouchDesigner)
- Never stored on disk, in a database, or in any persistent form
- Never transmitted to any external server, cloud service, or third party
- Discarded immediately after transmission — no logs, no history, no recordings

---

## Data Collection

**We do not collect any data. Period.**

- No personal information
- No usage analytics
- No crash reporting
- No device identifiers
- No advertising identifiers
- No cookies or tracking pixels
- No telemetry of any kind

The app contains no analytics SDKs, no third-party frameworks, and no network calls to any server other than the local IP address you manually configure.

---

## HealthKit Data

TDInput requests access to HealthKit to read heart rate data during an active workout session on your Apple Watch. This data is:

- Read in real time and forwarded over your local network as an OSC message
- Never written back to HealthKit (beyond the workout session itself)
- Never stored, cached, or logged by the app
- Never transmitted outside your local network

HealthKit access is optional. The app functions fully with iPhone sensors alone if you decline HealthKit permissions or do not have an Apple Watch.

---

## Local Network Usage

TDInput sends UDP packets containing sensor data to a local IP address and port that you specify. This communication:

- Occurs only on your local Wi-Fi network
- Uses the OSC (Open Sound Control) protocol — an open standard for real-time data
- Does not traverse the internet
- Does not connect to any remote servers
- Stops immediately when you close the app or toggle streaming off

---

## Third Parties

TDInput does not integrate with, send data to, or receive data from any third-party services. There are no:

- Analytics providers
- Advertising networks
- Cloud storage services
- Social media integrations
- Crash reporting services

The app is entirely self-contained.

---

## Data Retention

TDInput retains no data. The only information stored on your device is your configuration preferences (IP address and port number), saved locally via UserDefaults. These can be cleared by deleting the app.

---

## Children's Privacy

TDInput does not collect any data from any user, including children under 13. The app is rated 4+ and contains no objectionable content.

---

## Changes to This Policy

If this privacy policy is updated, the changes will be reflected in the "Last Updated" date above. As TDInput collects no data, meaningful changes to this policy are unlikely.

---

## Contact

If you have questions about this privacy policy, contact:

# Privacy Policy — TDLidar

**Last Updated: March 30, 2026**

## Overview

TDLidar is a depth streaming app developed by Aristides Lintzeris. This privacy policy explains how TDLidar handles your data.

**The short version: TDLidar does not collect, store, or transmit any personal data. Period.**

---

## Data Collection

TDLidar does **not** collect any data whatsoever. Specifically:

- **No personal information** is collected (name, email, phone number, etc.)
- **No usage analytics** or tracking of any kind
- **No crash reports** are sent to us or any third party
- **No advertising** or ad tracking
- **No cookies** or similar tracking technologies
- **No user accounts** — the app requires no sign-up or login
- **No data is sent to our servers** — we don't have servers

---

## Camera and Sensor Data

TDLidar requires access to your iPhone's front-facing TrueDepth camera to capture depth data. This data:

- Is processed **entirely on your device**
- Is streamed **only to your local Wi-Fi network** via the NDI protocol
- Is **never stored** on your device (no recordings, no cache, no logs)
- Is **never transmitted** outside your local network
- Is **never sent** to us or any third party

The depth stream is sent over your local network using the NDI (Network Device Interface) protocol to NDI-compatible software (like TouchDesigner) running on other devices on the same Wi-Fi network. This data never leaves your local network.

---

## Local Network Access

TDLidar requires local network access to stream depth data via NDI. This access is used exclusively for:

- Broadcasting the NDI video stream on your local network
- Allowing NDI receivers (like TouchDesigner) to discover and connect to the stream

No data is sent to the internet, to external servers, or to any party outside your local network.

---

## Third-Party Services

TDLidar does not use any third-party services, SDKs, or frameworks that collect data. The NDI SDK (by Vizrt/NDI) is used for local network streaming only and does not collect or transmit any data externally.

---

## Data Storage

TDLidar does not store any data on your device beyond its own app settings (depth mode preferences, frame rate, etc.). These settings are stored locally in the app sandbox and are deleted when you uninstall the app.

---

## Children's Privacy

TDLidar does not collect any data from anyone, including children under 13. The app is rated 4+ and contains no objectionable content.

---

## Changes to This Policy

If we make changes to this privacy policy, we will update the "Last Updated" date at the top of this page. Since TDLidar does not collect data, any future changes would only reflect new features or clarifications — not new data collection practices.

---

## Contact

If you have any questions about this privacy policy, you can reach us at:

- **GitHub:** https://github.com/aristideslintzeris/TDLidar
- **Developer:** Aristides Lintzeris



*This privacy policy applies to TDLidar version 2.0 and later.*


*TDInput is an independent app. Apple, Apple Watch, iPhone, TouchDesigner, and HealthKit are trademarks of their respective owners.*
