Wino Launcher

**A Windows launcher for Wino Client and Minecraft: Java Edition.**

Wino Launcher is an independent project that provides a dedicated installation of Minecraft, version selection, and access to the Wino Client Fabric mod. Players use their own Microsoft account and must have a valid Minecraft: Java Edition entitlement and profile.

![Wino Launcher interface preview](screenshot.png)

## Current status

**Version 0.1.1 — in development.**

The Windows installer and launcher interface have been built. Microsoft OAuth, Xbox Live, and XSTS authentication succeeded in a user test. Minecraft Services currently rejects the application's Client ID with **HTTP 403: Invalid app registration**. Approval for Minecraft Services access is required before the launcher can complete authentication and launch an authenticated game session.

The launcher is not presented as an approved or fully tested public release. Complete game installation and launch remain unverified while this access is blocked.

## Features

- A Windows installer with desktop and Start menu shortcuts.
- A dedicated game directory, separate from an existing Minecraft installation.
- Selection of supported Minecraft releases from Mojang's version catalogue.
- Wino Client on Minecraft **1.21.11**; other selectable versions use vanilla Minecraft without Wino modules.
- Installation support for Minecraft, Fabric where needed, and the required official Java runtime.
- Adjustable game memory and an optional custom Java path.
- Session and sign-in code expiry indicators, automatic session renewal, and diagnostic messages.

## Microsoft sign-in and API access

Authentication follows this sequence:

**Microsoft OAuth → Xbox Live → XSTS → Minecraft Services → Java entitlement and profile verification.**

Minecraft Services access is needed to obtain an authenticated Minecraft session, verify the player's Java Edition entitlement and profile, and launch the game for that player.

Players sign in on Microsoft's website. Wino Launcher does not ask for their Microsoft password and does not provide an offline authentication bypass.

## Local data and privacy

Settings, game files, and diagnostic messages are stored locally under:

```text
%APPDATA%\WinoLauncher
```

The Microsoft authentication cache is encrypted using Electron's Windows-backed secure storage. The Minecraft access token is held in memory. Authentication tokens are not sent to a Wino backend. The launcher is configured to omit authentication tokens and sign-in codes from its diagnostic log.

The application Client ID is configured by the project maintainer; players do not create their own Microsoft application registrations.

## Contact

For questions about this application, contact the repository owner through GitHub.

---

Wino Launcher is an independent project and is not affiliated with, endorsed by, or an official product of Mojang or Microsoft. Minecraft: Java Edition is required to play.
