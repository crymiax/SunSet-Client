# HEY PLEASE NOTE THIS

# ORIGINAL CLIENT ISN'T OUT YET YOU CAN USE THE FABRIC 1.21.11 MOD IN THE RELEASES
# STILL WAITING FOR MY AZURE ID TO GET APPROVED


# Sunset Client

A lightweight, standalone Minecraft: Java Edition launcher for Linux, written in C++.
Native **X11 and Wayland** support, animated sunset/fire interface, and two account modes.

## Features

- **Microsoft accounts**: sign in with the device-code flow (Xbox Live, XSTS, Minecraft services). Tokens refresh automatically.
- **Offline accounts**: play singleplayer or on offline-mode servers with any username.
- Downloads game versions, libraries, assets and natives, then launches the game.
- Picks the right Java version per Minecraft version automatically, or use your own path.
- Adjustable RAM and extra JVM arguments.
- Runs on both X11 and Wayland, chosen at runtime.

## Requirements

- Linux x86_64
- OpenGL 3.3 capable GPU and drivers
- `libcurl`, `unzip`
- A Java runtime (Java 21 recommended: `jdk21-openjdk` on Arch, `openjdk-21-jre` on Debian/Ubuntu)

## Usage

```
chmod +x sunset-client
./sunset-client              # Wayland if available, otherwise X11
./sunset-client --x11        # force X11
./sunset-client --wayland    # force Wayland
```

Pick or add an account, choose a version, press **PLAY**.

Data is stored in `~/.local/share/sunset-client/`.

## Privacy and authentication

- Microsoft sign-in happens on Microsoft's own page (microsoft.com/link). The launcher never sees your password.
- Tokens are stored locally in `config.json` (file permissions `600`) and sent only to Microsoft, Xbox Live and Mojang services.
- Sunset Client does not collect telemetry, show ads, or contact any other server.
- Game files are downloaded from Mojang's official servers.

## Not affiliated

Sunset Client is an independent project. It is not affiliated with, endorsed by, or associated with Mojang Studios or Microsoft. Minecraft is a trademark of Mojang Studios.

## Releases

Download the latest binary from the [Releases](../../releases) page.
