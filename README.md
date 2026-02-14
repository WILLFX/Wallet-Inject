# Wallet-Inject

One-button web page that opens MetaMask Mobile from Android Chrome and prefills a Sepolia ETH transfer using a MetaMask deeplink.

Live: https://willfx.github.io/Wallet-Inject/

## What it does
Tap the button to:
- open MetaMask
- set network to Sepolia (chainId 11155111)
- prefill recipient + amount
- you confirm the transaction in MetaMask

## How it works
It builds this deeplink and redirects the browser to it:

`https://link.metamask.io/send/<RECIPIENT>@11155111?value=<VALUE_WEI>`

`value` is in wei (1 ETH = 1e18 wei).

## Configure
Edit `index.html`:
- `RECIPIENT` = address to receive the test ETH
- `VALUE_WEI` = amount in wei

Examples:
- 0.0007 ETH → `700000000000000`
- 0.0006 ETH → `600000000000000`

## Notes
- Android Chrome doesn’t have an injected MetaMask provider, so the transfer is initiated through a deeplink.
- If MetaMask shows “Review alerts”, it’s usually due to a flagged recipient (e.g., 0x…dEaD) or insufficient balance for gas.
