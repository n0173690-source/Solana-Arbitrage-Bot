Solana Arbitrage Bot
A simple Solana onchain arbitrage bot for arbitrage opportunities. This bot calculate the most optimal trade size between various DEX pools on Solana and executes trades when profitable opportunities are found. This repository utilizes the onchain program for executing arbitrage trades.

This is a demo bot to show how to parse each pool and call the onchain program. This is NOT a fully functional bot. This is only recommanded for advanced users to use as a reference. For new users please use the full featured bot to get started:

Example transaction: https://solscan.io/tx/2JtgbXAgwPib9L5Ruc5vLhQ5qeX5EMhVDQbcCaAYVJKpEFn22ArEqXhipu5fFyhrEwosiHWzRUhWispJUCYyAnKT

Program: https://solscan.io/account/MEViEnscUm6tsQRoGd9h6nLQaQspKj7DB2M5FwM3Xvz

Features
Load configuration from a config file
Create ATA if not exist
Send transactions through multiple RPC endpoints (spam)
Kamino flashloan integration
Parse all available pool types (Raydium, DLMM, Whirlpool, etc.)
Supported Dexes
Pump AMM
Raydium V4
Raydium CPMM
Raydium CLMM
Meteora DLMM
Meteora Dynamic AMM
Meteora DAMM V2
Orca Whirlpool
SolFi
Vertigo
Getting Started
Prerequisites
Rust and Cargo installed
A Solana wallet with SOL
Installation
Clone the repository

git clone https://github.com/x89/Solana-Arbitrage-Bot.git
cd Solana-Arbitrage-Bot
Update config.toml file

Run the bot

cargo run --release --bin Solana-Arbitrage-Bot -- --config config.toml
Configuration
Copy the example configuration file:
cp config.toml.example config.toml
Edit config.toml and configure your:
Private key for your Solana wallet
RPC endpoint URL(s)
Configure your trading pairs and pools:
Update the mint_config_list with your desired token mints
Add the corresponding pool addresses for each DEX type (Raydium, DLMM, Whirlpool, etc.)
Ensure lookup table accounts are properly set for your trading pairs
Configuration Options
Bot Configuration
compute_unit_limit: Maximum compute unit limit per transaction
process_delay: Delay between processing iterations in milliseconds
Routing Configuration
mint_config_list: List of mints to process
mint: Mint address
raydium_pool_list: List of Raydium pool addresses
meteora_damm_pool_list: List of Meteora Dynamic AMM pool addresses
meteora_dlmm_pool_list: List of Meteora DLMM pool addresses
meteora_damm_v2_pool_list: List of Meteora DAMM V2 pool addresses
raydium_cp_pool_list: List of Raydium CP pool addresses
pump_pool_list: List of Pump pool addresses
whirlpool_pool_list: List of Whirlpool pool addresses
raydium_clmm_pool_list: List of Raydium CLMM pool addresses
solfi_pool_list: List of Solfi pool addresses
vertigo_pool_list: List of Vertigo pool addresses
lookup_table_accounts: List of lookup table accounts
process_delay: Process delay in milliseconds
RPC Configuration
url: RPC URL for the Solana network
Spam Configuration
enabled: Enable spam transactions
sending_rpc_urls: List of RPC URLs for sending transactions
compute_unit_price: Fixed compute unit price
max_retries: Maximum retries
enable_simple_send: Enable simple send mode
Wallet Configuration
private_key: Private key (can be path or environment variable)
Kamino Flashloan Configuration
enabled: Enable Kamino flashloan
License
MIT
