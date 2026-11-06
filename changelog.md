# v2.89.4

- Added a mod description, `about.md` and this changelog.
- The startup message in the console now shows the real mod version.
- Build files cleaned up: the CMake project is now called `ClickBeforeFrames`, iOS builds are forced to arm64, and the build presets use the new name.
- GitHub Actions now builds Windows, macOS, iOS, Android 32-bit and Android 64-bit and combines them into a single `.geode` package.
- Setting descriptions no longer say "F6", since the default stage key is `6`.
- Replaced `BUILD-MOBILE.md` with a complete `BUILDING.md`.
