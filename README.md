# Sunset Client

Standalone Minecraft launcher in C++17. GLFW 3.4 + Dear ImGui, native **X11 and Wayland**
(chosen at runtime), animated fire/sunset art, **cracked (offline)** and **online (Microsoft)** accounts.

## Dependencies

Arch:
```
sudo pacman -S --needed base-devel cmake curl wayland wayland-protocols libxkbcommon \
  libx11 libxrandr libxinerama libxcursor libxi mesa unzip jdk21-openjdk
```
Ubuntu / Debian:
```
sudo apt install build-essential cmake pkg-config libcurl4-openssl-dev libwayland-dev \
  wayland-protocols libxkbcommon-dev xorg-dev libgl1-mesa-dev unzip openjdk-21-jre
```
(GLFW, ImGui and nlohmann/json are downloaded by CMake automatically.)

## Build and run

```
cmake -S . -B build
cmake --build build -j
./build/sunset-client              # Wayland if available, else X11
./build/sunset-client --x11        # force X11 / XWayland
./build/sunset-client --wayland    # force Wayland
```

## Features

- Cracked accounts: any username, vanilla-compatible offline UUID, no login.
- Online accounts: Microsoft device-code login (Xbox Live, XSTS, Minecraft services), tokens auto-refresh.
- Downloads versions, libraries, assets and natives (8 parallel downloads), then launches the game.
- Auto-picks the right JDK per version from `/usr/lib/jvm` (Java 8/17/21...), or set your own path.
- Game keeps running if you close the launcher. Game output goes to `latest-game.log` and the log panel.
- All data in `~/.local/share/sunset-client/` (`config.json`, `versions/`, `libraries/`, `assets/`, `game/`).

## Microsoft login setup (one time)

Online login needs your own Azure app id:

1. portal.azure.com, App registrations, New registration.
2. Supported account types: "Personal Microsoft accounts only".
3. Authentication, Advanced settings, **Allow public client flows = Yes**.
4. Paste the Application (client) ID into Advanced, Azure client ID, in the launcher.

New app ids may also need Mojang's approval before the Minecraft services call works
(Mojang's third-party API access form). Until then, offline accounts work fine.

## Not included yet

Fabric/Forge profiles (`inheritsFrom`), mod management, skins, auto-update.
