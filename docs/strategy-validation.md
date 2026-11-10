# Independent Trading Strategy Validation

## The decision

Before deploying a strategy or allocating capital, understand which results are supported by evidence, which depend on fragile assumptions, and where the strategy may fail.

## What I examine

- Data provenance, completeness, and the integrity of the test setup.
- Look-ahead bias, leakage, selection effects, and overfitting.
- Execution assumptions: spreads, commissions, slippage, financing costs, and available liquidity where relevant.
- Drawdowns, tail exposure, concentration, and the behavior of grid or martingale structures where present.
- Robustness across time periods, market conditions, and reasonable parameter changes.
- Probabilities of explicitly defined outcomes where the available evidence and method support estimation.

The exact scope of a review depends on the decision and the evidence available. Not every procedure applies to every dataset.

## What you receive

- A clear assessment tied to the decision you need to make.
- The assumptions, inputs, and limitations behind the findings.
- Stress scenarios, failure conditions, and sensitivity to key assumptions.
- Probability estimates with their event definition, horizon, method, and uncertainty, where applicable.
- A practical list of what to fix, test next, or monitor.

## About probability estimates

An estimate must refer to a defined event over a defined horizon, under stated assumptions. Examples include exceeding a drawdown threshold or achieving a specified net result after costs.

Historical frequencies, simulated scenario probabilities, and calibrated predictive probabilities are different quantities. The report identifies which one is being presented. No estimate guarantees a future result.

## Research laboratory

Demonstrations and confidential reviews are arranged individually.

This page describes the consulting service. It is not a description of [Market Compass](https://github.com/TelelyukhinIgor/market-compass) or [Kronos Workbench](https://github.com/TelelyukhinIgor/kronos-workbench), which are separate published research tools.

## Confidentiality and first contact

Start with a short description of the strategy, the decision, and the evidence available. Confidential files are exchanged through an agreed private channel. Do not post code, account details, credentials, or trade histories in public GitHub issues.

[Email](mailto:igor@telelyukhin.com) · [LinkedIn](https://www.linkedin.com/in/igor-telelyukhin/)

Ljubljana, Slovenia · remote · English / Russian
