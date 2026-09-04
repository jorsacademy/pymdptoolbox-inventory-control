# PyMDPToolbox Inventory Control

A finite-state stochastic inventory-control example solved with `pymdptoolbox` using both Value Iteration and Policy Iteration.

## Problem

The state is on-hand inventory from `0` to `max_inventory`. The action is an order quantity from `0` to `max_order`. Demand follows a Poisson distribution. Unmet demand is treated as lost sales and incurs a penalty; remaining stock incurs holding cost, and replenishment incurs order cost.

The model builds:

- transition probabilities `P[A, S, S]`
- expected rewards `R[S, A]`
- discounted infinite-horizon policies solved with PyMDPToolbox

## Installation

```bash
python -m pip install -e '.[dev]'
```

## Run

```bash
pymdptoolbox-inventory
```

The CLI solves the same MDP with both algorithms and prints the order quantity chosen in each inventory state.

## Test

```bash
pytest
```

Tests validate stochastic matrices, configuration constraints, storage-capacity behavior, Value Iteration / Policy Iteration agreement, CLI output, and a minimum 90% project coverage threshold.

## Compatibility note

The upstream `pymdptoolbox` package is mature but old: its latest PyPI release is `4.0b3` from 2015. This repository therefore treats modern Python compatibility as something to verify continuously rather than assume. GitHub Actions tests Python 3.10 through 3.14 on every push and pull request.
