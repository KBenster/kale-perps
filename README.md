# KALE Perpetual Exchange

> A decentralized leveraged trading platform built on Stellar's Soroban smart contract platform, featuring KALE as the primary collateral asset.

[![Stellar](https://img.shields.io/badge/Stellar-Soroban-blue)](https://soroban.stellar.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Testnet](https://img.shields.io/badge/Network-Testnet-orange)](https://stellar.expert/explorer/testnet)

## Overview

KALE Perpetual Exchange is a sophisticated DeFi protocol that enables leveraged trading of digital assets using a pool-based market making model. Built on top of Zenex architecture, the platform uses standardized, tokenized vaults where each share represents proportional ownership of underlying assets.

### Key Benefits

- **Pool-based trading** - No order books, trade against vault liquidity
- **KALE collateral** - Native token integration with $1 USD peg
- **Stellar Passkeys** - Hardware-backed authentication without private keys
- **Up to 50x leverage** - Advanced margin system with automatic liquidations
- **Reflector oracles** - Tamper-resistant price feeds

## Architecture

### Core Smart Contracts

| Contract | Address | Description |
|----------|---------|-------------|
| **KALE Token** | `CAAVU2UQJLMZ3GUZFM56KVNHLPA3ZSSNR4VP2U53YBXFD2GI3QLIVHZZ` | ERC-20 compatible collateral token |
| **Oracle** | `CCQFLFIIP6VOTVWU3ENWZGRITY3UNAZT3SRPDF27JEAXNEVIGR3OA3IQ` | Reflector price feed integration |
| **Trading** | `CACR6U34NZEAROL7EEH22HHLEE6URKE43FB23CLLSOC3XZCMXUNM5Z2I` | Perpetual swap mechanics |
| **Vault** | `CCYALTIG7PMV7HSKXVWNBEKDCI6ED2N7SS2FNP322AIH35GFMVSMHWEG` | Liquidity pool management |
| **Share Token** | `CCPU63KOWDVITW442XCC6CBVMINZME4X2JD6IDAGNNS3ILRX7HVXVHBV` | Vault LP tokens |

### System Flow

```mermaid
graph TD
   A[Trader] -->|Deposit KALE| B[Trading Contract]
   C[LP] -->|Deposit KALE| D[Vault Contract]
   B -->|Get Price| E[Oracle Contract]
   B -->|Use Liquidity| D
   E -->|Reflector Data| F[External Price Feeds]
