# Futures Risk Toolkit (FRT)

> A web-based financial risk analytics dashboard for understanding futures exposure, tick-based loss calculation, margin utilization, and stress testing logic.

[![Live App](https://img.shields.io/badge/Live%20App-arham7s.github.io%2FFRT-00d4aa?style=flat-square&logo=github)](https://arham7s.github.io/FRT/)
[![Full Docs](https://img.shields.io/badge/Full%20Docs-README.html-3b82f6?style=flat-square)](https://arham7s.github.io/FRT/README.html)
[![Stack](https://img.shields.io/badge/Stack-HTML%20%2F%20CSS%20%2F%20JS-f59e0b?style=flat-square)]()

---

## Project Overview

The Futures Risk Toolkit is an educational prototype that demonstrates how exchange-style risk evaluation works at the trade level. It converts market price movements into monetary risk, helping users understand:

- How stop loss placement determines maximum possible loss
- How futures contract specifications impact exposure
- Why margin is different from actual risk
- How extreme market shocks affect trading capital

Inspired by simplified workflows used in derivatives exchanges, clearing corporations, and brokerage risk management desks.

---

## Core Concept — Tick-Based Risk

Futures contracts move in minimum price increments called **ticks**. Each tick has a fixed monetary value — meaning even small price movements can result in significant financial gains or losses.

```
Price Movement → Tick Movement → Monetary Risk
```

---

## Trade Risk Calculation Logic

### Step 1 — Price Risk
```
Price Risk = | Entry Price − Stop Loss Price |
```
Maximum adverse market move tolerated.

### Step 2 — Ticks at Risk
```
Ticks at Risk = Price Risk / Tick Size
```
Number of minimum price movements at risk.

### Step 3 — Risk per Contract
```
Risk per Contract = Ticks at Risk × Tick Value
```
Maximum possible loss on one futures contract.

### Step 4 — Total Trade Risk
```
Total Trade Risk = Risk per Contract × Number of Contracts
```
Total potential financial exposure of the trade.

---

## Understanding Margin vs Risk

Futures trading requires depositing **initial margin** as collateral. However:

> ⚠️ **Margin is NOT the maximum possible loss.**

The toolkit highlights situations where:
- Trade risk exceeds margin requirement
- Trader capital may be insufficient
- Potential default exposure can arise

---

## Stress Testing Engine

Simulates adverse market scenarios using simplified SPAN-style logic.

| Scenario | Shock |
|----------|-------|
| Mild stress | −2% market move |
| Moderate stress | −5% volatility shock |
| Extreme stress | −10% event |
| Custom | User-defined |

**Shocked Price Formula (Long Positions):**
```
Shocked Price = Entry Price × (1 − Shock %)
```

---

## Position Sizing Logic

```
Allowed Risk      = Account Capital × Risk %
Contracts Allowed = ⌊ Allowed Risk / Risk per Contract ⌋
```

Ensures capital preservation, controlled drawdowns, and disciplined trading behaviour.

---

## Key Features

- Tick-accurate trade risk estimation
- Support for long and short futures positions
- Margin requirement comparison
- Stress scenario loss simulation
- Contract specification reference panel
- Financial dashboard-style UI

---

## Learning Outcomes

- Futures contract mechanics
- Relationship between leverage and risk
- Monetary impact of stop loss placement
- Scenario-based risk thinking
- Basic exchange-style margin logic

---

## Technology Stack

`HTML` `CSS` `JavaScript` `GitHub Pages`

---

## Author

**Arham Shah** — Engineering Student, Financial Risk Analytics  
GitHub: [github.com/arham7s](https://github.com/arham7s)

---

> **Disclaimer:** This project is intended only for educational and analytical purposes. It does not represent official margin methodologies of any exchange or clearing corporation. Trading derivatives involves substantial financial risk.
