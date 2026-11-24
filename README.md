<div align="center">

# fbn4droid

**Arcade emulation for Android, with Lua scripting, training tools and rollback netplay.**

Built on [FinalBurn Neo](https://github.com/finalburnneo/FBNeo) with a native Android interface, plus a separate MAME section.

[**Download the latest APK**](../../releases/latest) · [Release notes](../../releases) · [Report a problem](../../issues)

</div>

---

## Highlights

- **FinalBurn Neo with Lua** – the real FBNeo SDL2 frontend and its Lua engine (not the libretro core), so community scripts such as the 3rd Strike training mode run as they do on desktop.
- **MAME section** – a second emulator inside the same app, switched from the side menu.
- **Game library** – search, grid or strip layout, filters by system (CPS-1, CPS-2, CPS-3, Neo Geo, …) and genre (Fighting, Beat 'em up, Shooter, …), and cover art downloaded automatically or picked from your phone.
- **Training and trial scripts, one tap** – 3rd Strike training mode, JoJo's Bizarre Adventure training mode and the Crystal Cube 99 combo trials are downloaded and set up from the game's Lua menu.
- **In-game tools** – pause menu with save states, DIP switches, service/test menu, cheat list (switch on/off, choose options, add your own, load `.ini`/`.dat` files), TAS tools panel (including a real freeze).
- **Controls** – full controller and keyboard support with remapping for two players, and an editable on-screen layout (move, resize, add buttons and macros).
- **Netplay** – local multiplayer over Wi-Fi or hotspot, and rollback online play (experimental).
- **Made for phones** – landscape and portrait layouts, full-screen interface, performance presets for weaker devices, on-screen FPS and speed counters.
- **Themes and languages** – 11 colour themes plus a custom one; English, Português (Brasil) and العربية (right-to-left).
- **Updates inside the app** – Settings → Help and about → *Check for updates*.

## Install

1. Open the [latest release](../../releases/latest) on your phone and download **`fbn4droid.apk`**.
2. Open the file and allow installs from your browser or file manager when Android asks.
3. Start the app and choose the folder that holds your ROMs.

Requires Android 8.0 or newer on a 64-bit (arm64) device. Later versions can be installed from inside the app; your games, saves and settings are kept.

> **ROMs are not included.** fbn4droid does not ship or download game ROMs. Use ROM sets you are legally entitled to use, in the set versions FinalBurn Neo expects.

## Folders on the phone

Default location: `/storage/emulated/0/Emulators/fbneo/`

| Folder | Contents |
| --- | --- |
| `lua/` | Lua scripts and their resources, one folder per script pack |
| `config/` | Settings, controller maps, save states |
| `covers/` | Downloaded or imported cover art (hidden from the gallery) |
| `last_run.log` | Log of the last game, for bug reports |

The folder is still named `fbneo` so that saves from earlier versions keep working.

## Reporting a problem

Open an [issue](../../issues) and attach the log from **Settings → Help and about → Last game log**. Please mention your phone model, Android version and the game.

## Building from source

The repository keeps the app's complete source as `project.zip`; pushing a new `project.zip` makes GitHub Actions build and publish the APK.

1. `project.zip` contains the Android project, `build-android.sh`, the MAME host code and `patches/fbneo-android.patch`.
2. The workflow (`.github/workflows/build.yml`) unpacks it and runs `build-android.sh`, which fetches FinalBurn Neo at a pinned commit, applies the patch, builds FBNeo and SDL2 for arm64 and packages the APK.
3. The result is published as the `latest` release, named `fbn4droid.apk`.

To build locally you need a Linux machine with the Android SDK and NDK, JDK 17, Gradle 8.7+, CMake, Ninja, Perl, GCC/G++ and Git. Unzip `project.zip` and run `bash build-android.sh`.

## Credits

- Created by **Hexie**.
- [FinalBurn Neo](https://github.com/finalburnneo/FBNeo) and its contributors – the emulation core.
- [Fightcade FBNeo](https://github.com/fightcadeorg/fightcade-fbneo) – reference for the Lua and rollback features.
- [SDL2](https://libsdl.org/) and [Lua](https://www.lua.org/).
- [libretro](https://www.libretro.com/) and the MAME team – the MAME section.
- Training and trial scripts are the work of their own authors (3rd Strike training mode, JoJoban training mode by maximusmaxy, 3rd Strike trials by Crystal Cube 99). The app only downloads and sets them up for you.
- Cover art comes from the [libretro thumbnails](https://github.com/libretro-thumbnails) project.

## Licence

FinalBurn Neo is distributed under its own licence, which does not allow commercial use; see the [upstream repository](https://github.com/finalburnneo/FBNeo/blob/master/src/license.txt). Anything built from it must respect those terms. fbn4droid is not affiliated with FinalBurn Neo, Capcom, SNK or any other rights holder.
