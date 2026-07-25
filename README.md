<div align="center">
  <img
    height="148"
    src="/actioner.png?size=148"
    alt="Actioner logo"
  />
</div>

<h1 align="center">Actioner</h1>

<p align="center">
  Give Apple Shortcuts access to useful device actions, sensors, and system features.
</p>

<p align="center">
  <img alt="Swift 6" src="https://img.shields.io/badge/Swift-6-F05138?logo=swift&logoColor=white">
  <img alt="iOS 26+" src="https://img.shields.io/badge/iOS-26%2B-000000?logo=apple&logoColor=white">
  <img alt="Version 0.0.8" src="https://img.shields.io/badge/version-0.0.9-yellow">
  <a href="./LICENSE"><img alt="Apache 2.0 License" src="https://img.shields.io/badge/license-Apache--2.0-blue"></a>
</p>

### Actioner is currently an **alpha preview**. Features, action names, and behavior may change, and some actions may require the app to open so iOS can request permission.

## About

Actioner is an iPhone and iPad utility built with SwiftUI and App Intents. It extends Apple Shortcuts with actions that expose hardware feedback, biometric authentication, motion data, ambient sound estimates, camera access, and notifications.

The project is currently known as **Actioner Alpha Preview**, version **0.0.8**, codename **PrimimâGradus**.

## Available actions

| Action | Category | Result |
| --- | --- | --- |
| Try Demo | Test | Runs the demo action |
| StringOutput | Test | Returns the supplied text |
| OpenCam | Test | Opens the camera interface |
| Light Feedback | Haptic Feedback | Plays light haptic feedback |
| Medium Feedback | Haptic Feedback | Plays medium haptic feedback |
| Heavy Feedback | Haptic Feedback | Plays heavy haptic feedback |
| Rigid Feedback | Haptic Feedback | Plays rigid haptic feedback |
| Auth | Authenticate | Returns `true` or `false` after biometric authentication |
| Get Device Motion | Information | Returns accelerometer data as JSON |
| Get Ambient Decibels | Information | Returns an estimated ambient sound level |
| Notify Feedback | Test | Schedules a local notification with a title, body, and delay |

Example output from **Get Device Motion**:

```json
{
  "X": 0.01,
  "Y": -0.02,
  "Z": -0.99,
  "TotalG": 0.99025
}
```

## Requirements

- iPhone or iPad running iOS/iPadOS 26 or later
- Swift 6
- Xcode with the iOS 26 SDK, or a compatible version of Swift Playgrounds
- An Apple development team for installation on a physical device

## Getting started

1. Clone the repository:

(Note: this repo is Private)

   ```bash
   git clone https://github.com/TheActioner/Actioner-App.git
   cd Actioner-App
   ```

2. Open `Package.swift` in Xcode or Swift Playgrounds.
3. Select your development team and, if necessary, replace the bundle identifier with one available to your account.
4. Build and run Actioner on an iPhone or iPad.
5. Open Apple Shortcuts, add a new action, and search for **Actioner**.

For actions that use protected system features, launch Actioner at least once and approve the requested permissions.

## Permissions

Actioner requests only the permissions needed by the action being used:

| Permission | Used for |
| --- | --- |
| Camera | OpenCam |
| Face ID / biometrics | Auth |
| Microphone | Get Ambient Decibels |
| Motion & Fitness | Get Device Motion |
| Notifications | Notify Feedback |

Permission availability and behavior may differ between devices. The camera action falls back to the photo library when a camera is unavailable, such as in the simulator.

## Project structure

| File | Purpose |
| --- | --- |
| `MyApp.swift` | SwiftUI application entry point |
| `Intents.swift` | App Intents exposed to Apple Shortcuts |
| `Func.swift` | Haptics, authentication, motion, and sound helpers |
| `Cam.swift` | Camera and photo-library interface |
| `Info.swift` | Version, license, and maintainer metadata |
| `Package.swift` | App package and capability configuration |
| `WHATSNEW.md` | Release notes |

## Contributing

Issues, ideas, and pull requests are welcome. When adding a new action:

1. Keep the action focused on one task.
2. Add a clear title, description, category, and search keywords.
3. Request only the permissions the action actually needs.
4. Document its inputs and output in this README.
5. Test it both inside Apple Shortcuts and in the Actioner app.

## License

Actioner is available under the [Apache License 2.0](./LICENSE).

Copyright © 2026 Eymen Alvis Yıldırım.
