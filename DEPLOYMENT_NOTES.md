# Deployment notes (BAZA)


## Verify again (after upgrades)

Source of truth for bytecode: **`contracts/BazaToken.sol`**, contract name **`BazaToken`**. The nested **`contract/`** Foundry app is a different stack (OZ `BAZA`); do not mix them for this token.

- **Foundry (repo root):** `foundry.toml` + `./scripts/verify-baza-token.sh <address>` — see script header and `ETHERSCAN_API_KEY`.
- **Basescan UI:** [Verify contract](https://basescan.org/verifyContract).

## Farcaster Mini App manifest

- File: `public/.well-known/farcaster.json` → `https://baza-mining-app.vercel.app/.well-known/farcaster.json`
- **Warpcast:** Manifests → Create → domain `baza-mining-app.vercel.app` → **Verify**
- **`accountAssociation`** must be signed (empty placeholders in repo until you generate them):
  - [Farcaster Developers](https://farcaster.xyz/~/developers) or Base manifest signer
  - Paste `header`, `payload`, `signature` into the JSON, then redeploy
- **Emulator:** test URL `https://baza-mining-app.vercel.app` before publishing
- Icon spec: 1024×1024 PNG (replace `public/logo.png` when you have final art)

## Optional

- Proxy / implementation addresses if you upgrade later
