# Polygon Arbitrage Opportunity Detector (Rust)

This project is a simple arbitrage detector that polls two UniswapV2-style DEX routers on the Polygon network and logs potential arbitrage opportunities to a local SQLite database.

⚠️ **Disclaimer:**  
This is a simulation/prototype. It does **not** execute trades and does not consider slippage, router permissions, token approvals, or real gas estimation beyond a simplified constant gas cost.

---

## 🚀 Features
- Periodically queries two DEX routers for a token pair price (WETH/USDC by default)
- Detects price differences and computes a simulated profit for a fixed trade size
- Stores detected opportunities into a local SQLite database
- Easy configuration via `Config.toml`

---

## 📂 Project Files
- `Cargo.toml` — Rust dependencies
- `Config.toml.example` — example configuration file
- `src/main.rs` — main entrypoint and loop
- `src/config.rs` — configuration loader
- `src/dex.rs` — DEX router bindings and price fetch logic
- `src/arbitrage.rs` — arbitrage detection and profit calculation
- `src/db.rs` — SQLite storage
- `src/utils.rs` — utility functions (U256 ↔ f64 conversion)

---

## ⚙️ Quickstart

### 1. Install Prerequisites
- [Rust](https://rustup.rs/) (with Cargo)
- SQLite (optional, for inspecting the database)
- A Polygon RPC URL (free: [https://polygon-rpc.com](https://polygon-rpc.com) or via Infura/Alchemy)

Check Rust install:
```bash
rustc --version
cargo --version
