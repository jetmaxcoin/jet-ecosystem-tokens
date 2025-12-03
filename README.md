# Jet Ecosystem Token List

Token list for the Jet ecosystem on BNB Smart Chain, covering the JET MAX (`JET`) and Jet USD (`JETUSD`) tokens plus their logos for wallets, explorers, and DApps.

- `list.json` — token metadata (name, symbol, address, chainId, decimals, logoURI) with list name, timestamp, version, tags, and keywords.
- `logo/jetmax.png`, `logo/jetusd.png` — square PNG logos referenced by `logoURI`.

## How to use

- Fetch the list directly: `https://raw.githubusercontent.com/jetmaxcoin/jet-ecosystem-tokens/main/list.json`
- Example (JavaScript):
  ```js
  const url = 'https://raw.githubusercontent.com/jetmaxcoin/jet-ecosystem-tokens/main/list.json';
  const tokens = await fetch(url).then(r => r.json());
  console.log(tokens.tokens); // array of token entries
  ```

## Adding or updating tokens

1. Add the token entry to `tokens` with `name`, `symbol`, `address` (checksum preferred), `chainId`, `decimals`, and `logoURI` pointing to the hosted PNG.
2. Place a square PNG logo in `logo/` (200–512 px recommended) and reference it via `logoURI`.
3. Bump `version` using semver (patch for metadata fixes, minor for new tokens, major for breaking removals) and refresh the ISO 8601 `timestamp`.
4. Validate JSON before committing:
   ```bash
   python -m json.tool list.json
   # or
   jq . list.json
   ```
