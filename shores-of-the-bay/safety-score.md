---
description: A relative rating system for yield farms listed on YieldBay
---

# 🚧 Safety Score

## Description

This algorithm arrives at a final score for each farm by summing up the parameters described below according to their weights.

The final scores are then normalized to be more presentable & user-friendly.

| TVL        | 45% |
| ---------- | --- |
| Base APR   | 20% |
| Reward APR | 15% |
| Rewards    | 20% |

## Parameters <a href="#parameters" id="parameters"></a>

### TVL - 45% weightage <a href="#tvl-45-weightage" id="tvl-45-weightage"></a>

A fixed score is assigned out of 1 based on the liquidity range the farm lies in.

**Liquidity ranges:**

| Liquidity    | Score |
| ------------ | ----- |
| > $10M       | 1     |
| $1M - $10M   | 0.85  |
| $100k - $1M  | 0.75  |
| $10k - $100k | 0.6   |
| $1k - $10k   | 0.5   |

The above ranges and scores we’ve arrived on by simulating different ranges on the data. These might not be ideal, but will work for the time being.

> Caveat: The ranges and the scores will need to be updated as the ecosystem grows.

### Base APR - 20% weightage <a href="#base-apr-20-weightage" id="base-apr-20-weightage"></a>

Normalized percentile-based scores for the base APR.

1. The highest base APR farm gets a score of 1.
2. The score for the rest of the farms is calculated by dividing their base APR by the highest base APR.

We don’t have the base APRs for a lot of Stable AMM farms and there exists no concept of base APR for single-staking farms. Hence, they get a fixed score.

* Stable AMM - 0.6
* Single Staking - 0.3

### Reward APR - 15% weightage <a href="#reward-apr-15-weightage" id="reward-apr-15-weightage"></a>

Normalized percentile-based scores for the reward APR.

1. The highest reward APR gets a score of 1.
2. The score for the rest of the farms is calculated by dividing their reward APR by the highest reward APR.

### Rewards - 20% weightage <a href="#rewards-20-weightage" id="rewards-20-weightage"></a>

Normalized percentile-based scores for the absolute USD value of rewards being disbursed in the farm per day.

1. The highest reward USD value gets a score of 1.
2. The score for the rest of the farms is calculated by dividing their reward USD value by the highest reward USD value.

## Future Work <a href="#future-work" id="future-work"></a>

This algorithm should eventually evolve to include parameters like:

* Impermanent loss risk in the farm
* Quality of assets in the farm
* Etc.

We’ve started sowing the seeds for the same by scoping out the work for a v2 of our [Assets Repository](https://github.com/yield-bay/assets) to include the data for the assets that we’d need to make the scoring algorithm more robust.\
