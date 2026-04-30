# Privacy Policy — TDLidar

**Last Updated: April 30, 2026**
*Applies to TDLidar 6.0 and later, including the optional TDLidar Watch App companion.*

## Overview

TDLidar is a real-time capture suite developed by Aristides Lintzeris for streaming depth, camera, motion, audio, and tracking data from an iPhone (and optionally an Apple Watch) into TouchDesigner, OBS, Resolume, and other NDI / OSC receivers on the same Wi-Fi network. NDI SDK Is only used to send video over the local network

**The short version: TDLidar does not collect, store, or transmit any personal data off your local network. Period.**

There is no account, no analytics, no cloud, no third-party SDK that phones home. The app operates entirely on your device and on your local Wi-Fi.

---

## What TDLidar does NOT do

- **No personal information** is collected (name, email, phone number, etc.)
- **No usage analytics** or telemetry of any kind
- **No crash reports** are sent to us or any third party
- **No advertising** or ad tracking
- **No cookies** or similar tracking technologies
- **No user accounts** — the app requires no sign-up or login
- **No data is sent to our servers** — we don't have servers
- **No biometric identification** — TDLidar does not use Face ID or any face-recognition feature
- **No sharing of TrueDepth or face data with third parties** — depth maps and ARKit face data never leave your device except as live OSC / NDI on your own local Wi-Fi
- **No reading of your existing photos or videos** — Photos access is write-only

---

## Data TDLidar accesses, and why

All of the following is processed in real time, on-device, and emitted only to receivers on your local Wi-Fi network. Nothing is stored long-term unless you explicitly tap "Record" or "Save".

### Camera (NSCameraUsageDescription)

- **Front TrueDepth camera** — used for the depth video stream (NDI) and ARKit Face Tracking mode.
- **Rear LiDAR scanner** (Pro iPhones) — used as an alternative depth source.
- **Regular cameras** — used for the optional RGB NDI stream (v5.2+) and as the visual reference for ARKit body and hand tracking.

The camera image is processed in memory and sent to NDI receivers on your local network. It is never recorded or written to disk unless you explicitly start a recording (see *Recording* below).

### TrueDepth API + ARKit Face Tracking

When you enable Face mode on the Tracking page, TDLidar uses ARKit's `ARFaceTrackingConfiguration` to compute:

- 52 ARKit blend-shape coefficients (e.g., `browInnerUp`, `eyeBlinkLeft`, `jawOpen`)
- The 4×4 face transform matrix

This **face data** is used solely as live OSC control data under `/tdlidar/face/*` for visual / interactive applications. It is **not stored, not used for identification, and not transmitted off your local Wi-Fi network**. No face image, no face mesh geometry, no Face ID hash leaves the app.

### Microphone (NSMicrophoneUsageDescription)

When Audio or Transcription mode is active, the microphone feed is processed in real time for:

- **Audio analysis** — FFT spectrum, bass / mid / high levels, beat detection, dynamics, all streamed under `/tdlidar/audio/*`
- **Speech recognition** (when in Transcription mode) — see below

Audio buffers are processed in-memory and discarded each frame. They are **not recorded, not stored, and not transmitted off the device** other than as derived OSC values on your local Wi-Fi.

### Speech Recognition (NSSpeechRecognitionUsageDescription)

When Transcription mode is active, TDLidar uses Apple's on-device speech recognition (`SpeechAnalyzer` on iOS 26+, falling back to `SFSpeechRecognizer`) to convert speech to text. Recognition happens entirely on the device — **audio is never sent to Apple or any third-party server**. Recognized words are streamed as OSC under `/tdlidar/speech/*` and are not stored.

### Motion Sensors (NSMotionUsageDescription)

When Motion mode is active, TDLidar reads:

- Accelerometer
- Gyroscope
- Magnetometer (compass)
- Barometer / altitude
- Battery level

These values are streamed as live OSC under `/tdlidar/motion/*`. No motion history is recorded.

### Local Network (NSLocalNetworkUsageDescription, NSBonjourServices)

TDLidar publishes itself as an NDI source via Bonjour (`_ndi._tcp` / `_ndi._udp`) on your local Wi-Fi so NDI receivers (TouchDesigner, OBS, Resolume, vMix) can discover it. OSC messages are sent as UDP to the IP and port you configure in Settings. **No traffic leaves your local network.**

### Recording (NSPhotoLibraryAddUsageDescription)

When you tap the record button on the LiDAR page, TDLidar writes the colormapped NDI depth output to an `.mp4` video file inside the app's private storage (`Documents/NDIRecordings/`). These files are visible only to TDLidar; they are not synced to iCloud unless you have iCloud Backup enabled at the device level.

When you open the Recordings folder in the app and tap "Save" on a clip, TDLidar uses **write-only Photos access** (`PHPhotoLibrary.requestAuthorization(for: .addOnly)`) to copy that single clip into your Photos library. TDLidar **cannot read your existing photos or videos** — the access is strictly write-only and limited to clips you explicitly export.

You can delete recordings from inside the app at any time. Uninstalling TDLidar removes the in-app recordings; clips already exported to Photos remain in Photos until you delete them.

---

## Apple Watch Companion (optional)

The TDLidar Watch App is an **optional** companion. Users without an Apple Watch never see it. When installed and active, the watch app reads:

- **Motion sensors** (`CMMotionManager`) — wrist orientation, accel, gyro
- **HealthKit** — heart rate during a foreground workout session (Active Energy is also written so the workout session stays alive)

These values are sent over Apple's `WCSession` (Bluetooth / Wi-Fi peer link to the paired iPhone), where the iPhone-side `PhoneSessionManager` republishes them as OSC under `/tdlidar/watch/*`.

The watch app:
- Does **not** transmit data over its own internet connection
- Does **not** store sensor or health data anywhere
- Uses HealthKit only as an in-memory live source — no records are written to your Health app other than the workout session itself, which is required by Apple to keep the heart-rate stream open

---

## Data storage

TDLidar stores the following on your device only:

- **App settings** (depth mode, frame rate, NDI options, motion sensitivity, etc.) in the iOS settings sandbox. Removed when you uninstall the app.
- **Welcome-screen "seen" flag** in `UserDefaults`. Removed when you uninstall.
- **NDI Recordings** in the app's `Documents/NDIRecordings/` folder when you tap Record. You control these — delete them in the Recordings view inside TDLidar, or by uninstalling the app.

No personal data, no sensor history, no user-identifying information is stored.

---

## Third-party software

TDLidar uses the following third-party software, none of which collects user data:

- **NDI® SDK** by Vizrt NDI AB — used solely for local-network video transport. No analytics, no internet calls.
- **Apple frameworks only** for everything else (AVFoundation, ARKit, CoreMotion, CoreLocation–not used, HealthKit on watch, SpeechAnalyzer / SFSpeechRecognizer, Photos, Vision, CoreML).

NDI® is a registered trademark of Vizrt NDI AB.

---

## Children's Privacy

TDLidar does not collect any data from anyone, including children under 13. The app is rated 4+ and contains no objectionable content.

---

## Changes to This Policy

If we make changes to this privacy policy, we will update the "Last Updated" date at the top of this page. Since TDLidar does not collect data, future changes would only reflect new features or clarifications — not new data collection practices.

---

## Contact

If you have any questions about this privacy policy, you can reach us at:

- **GitHub:** <https://github.com/aristideslintzeris/TDLidar>
- **Developer:** Aristides Lintzeris

---
