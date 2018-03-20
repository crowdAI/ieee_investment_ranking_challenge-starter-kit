# ieee_stock_prediction_challenge-starter-kit
![CrowdAI-Logo](https://github.com/crowdAI/crowdai/raw/master/app/assets/images/misc/crowdai-logo-smile.svg?sanitize=true)

Starter kit for getting started in the [IEEE Investment Ranking Challenge](https://www.crowdai.org/challenges/ieee-investment-ranking-challenge).

# Introduction
**TODO**

# Access Dataset
**TODO**

# Problem Statement
**TODO**

# Baselines
**TODO**

# Insallation

```
pip install --upgrade crowdai
```
**Note** : This challenge expects atleast `crowdai` client version `1.0.17`

# Usage
```
import crowdai
api_key = "YOUR CROWDAI API KEY HERE"
challenge = crowdai.Challenge("IEEEInvestmentRankingChallenge", api_key)
result = challenge.submit("sample_submission.csv")
print(result)
```

# Author
SP Mohanty <sharada.mohanty@epfl.ch>
