# Building

This project targets Geometry Dash 2.2081 and Geode 5.11.x (see `mod.json`). The pause menu's **Buffer** button works with touch input, so a keyboard is not needed on mobile.

## Requirements

- CMake 3.21 or later and Ninja
- A Geode SDK checkout that matches `mod.json`, with the `GEODE_SDK` environment variable pointing to it
- The Geode CLI on your `PATH`
- Android: Android NDK (r29 was used for these presets). Geode needs Android API 23 or newer.
- iOS and macOS: a Mac with Xcode. Windows cannot produce an iOS or macOS binary.

## Easiest: GitHub Actions

Push the repository to GitHub. `.github/workflows/build.yml` builds Windows, macOS, iOS, Android 32-bit and Android 64-bit, then combines them into one `.geode` file. Download it from the run's artifacts (**Build Output**, kept for 14 days). You can also start it by hand with **Run workflow**.

## Geode CLI

Run these in the project folder.

```sh
# Windows or macOS (current platform). If you use Clang and Ninja, add --ninja
geode build

# Android: install the Geode binaries once, then build
geode sdk install-binaries -p android64
geode sdk install-binaries -p android32
geode build -p android64
geode build -p android32

# iOS (Mac with Xcode)
geode sdk install-binaries --platform ios
geode build -p ios
```

For the CLI's Android build, set `ANDROID_NDK_ROOT` to the NDK folder. On Windows, Ninja must be installed.

Output goes to a `build-<platform>` folder, for example `build-android64`.

## CMake presets (no Geode CLI build step)

The presets in `CMakePresets.json` call CMake directly. They need the Geode binaries to be installed first (the `geode sdk install-binaries` commands above) and use `ANDROID_NDK_HOME` instead of `ANDROID_NDK_ROOT`.

PowerShell, Android:

```powershell
$env:GEODE_SDK = "C:\path\to\geode-sdk"
$env:ANDROID_NDK_HOME = "C:\path\to\android-ndk"
cmake --preset android64
cmake --build --preset android64-package
cmake --preset android32
cmake --build --preset android32-package
```

macOS, iOS:

```sh
export GEODE_SDK="/path/to/geode-sdk"
cmake --preset ios
cmake --build --preset ios-package
```

Packages are written to `build/android64/`, `build/android32/` and `build/ios/` as `pulse.input-buffer.geode`.

## Installing the package

- **Windows:** copy the `.geode` file to `geode/mods` inside the Geometry Dash folder.
- **Android:** copy it to `/storage/emulated/0/Android/media/com.geode.launcher/game/geode/mods/`.
- **iOS:** transfer the `.geode` file to the device and install it with Geode's mod installer.

Restart the game after installing.
