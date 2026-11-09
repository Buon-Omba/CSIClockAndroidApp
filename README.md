# CSI CLOCK
A simple Kotlin clock used for uphill bike time trials. For now it's Android-only.

It is used at the start line of uphill time trials organized by CSI Frosinone and Speedpass Lazio: the phone shows the official time and plays the start countdown, so riders and timekeepers share the same reference.

## Features

- Large clock with millisecond precision (`HH:mm:ss.SSS`), readable from a distance in both portrait and landscape.
- Audible start countdown: short beeps at 10 seconds and then every second for the last 5 seconds before each start.
- Long beep at every start slot (every 10 minutes: :00, :10, :20, …).
- Organization logo at the top of the screen.

## Tech stack

- Kotlin and Jetpack Compose (Material 3)
- Coroutines for the clock loop, `MediaPlayer` for the beeps
- Android 10 (API 29) or later

## Build (Arch Linux and derivatives)

```bash
sudo pacman -S --needed jdk17-openjdk android-tools
yay -S android-sdk-cmdline-tools-latest android-sdk-platform-tools android-platform
export ANDROID_HOME=/opt/android-sdk
sdkmanager --licenses

./gradlew assembleDebug
adb install -r app/build/outputs/apk/debug/app-debug.apk
```

## Next steps

- Create a Windows version
