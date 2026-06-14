# HELIOS CODEX Protocol Specification v1.0

## 1. Stablecoin Mechanics

### Minting
```
Deposit $200 RWA → ATLAS verifies collateral via VULCAN → Mint 100 HELIOS
Collateral ratio maintained at ≥200%
Real-time audit trail via zk-proofs
```

### Burning
```
Burn 100 HELIOS → ATLAS triggers redemption → Receive $100 RWA (at current value)
ATLAS rebalances remaining collateral
```

### Peg Defense Cascade
```
±0.3% deviation  → ATLAS alert → ARCHON armed
±0.5% deviation  → L1: Arbitrage bots ($10B flash liquidity) deployed
±1.0% deviation  → L2: Collateral rebalance + L3: Tx throttle + Insurance Fund
±2.0% deviation  → Emergency committee vote via CODEX governance
```

## 2. Collateral Basket

| Asset Class | Target Allocation | Rebalance Threshold |
|---|---|---|
| Real Estate (tokenized) | 40% | ±5% |
| Gold (physical + tokenized) | 30% | ±3% |
| T-Bills / Sovereign Credit | 20% | ±2% |
| Liquid (stablecoins, cash) | 10% | ±1% |

## 3. Governance

CODEX token holders vote on:
- Collateral basket adjustments
- Fee parameter changes
- Protocol upgrades proposed by ORACULUM
- Emergency actions requiring human override

Voting power: 1 CODEX = 1 vote (quadratic voting for large holders)

## 4. Revenue Distribution

```
Protocol Revenue
├── 50%: HELIOS stakers (yield)
├── 30%: CODEX burn (deflationary)
├── 15%: Treasury
└── 5%:  Insurance Fund
```

## 5. Security Layers

1. VULCAN post-quantum cryptography on all key operations
2. BFT consensus across 51 nodes (tolerates up to 17 faulty)
3. zk-SNARK proof-of-reserves published hourly
4. Formal verification of all DAEDALUS-deployed contracts
5. ORACULUM adversarial fuzzing on every upgrade
