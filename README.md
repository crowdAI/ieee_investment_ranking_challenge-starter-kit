# ieee_investment_ranking_challenge-starter-kit
![CrowdAI-Logo](https://github.com/crowdAI/crowdai/raw/master/app/assets/images/misc/crowdai-logo-smile.svg?sanitize=true)

[![gitter-badge](https://badges.gitter.im/crowdAI/crowdAI/ieee-investment-ranking-challenge.png)](https://gitter.im/crowdAI/crowdAI/ieee-investment-ranking-challenge)

Starter kit for getting started in the [IEEE Investment Ranking Challenge](https://www.crowdai.org/challenges/ieee-investment-ranking-challenge).

# Introduction
Using the provided data sets of financial predictors and semi-annual returns, participants are challenged to develop a model that will help identify the best-performing stocks in each time-period.

Research Question: **Which stocks will experience the highest and lowest returns during the next six months?**   

Out of the thousands of stocks in the market, small groups will experience exceptionally high or low returns. Considering the distribution of stock returns, a portfolio manager must buy the stocks in the right tail of the distribution and avoid the stocks in the left tail. The performance of an entire equity portfolio is often driven by these key investment decisions. **The goal of this challenge is to explore methodology that will increase the probability that portfolio managers identify these stocks with extreme positive or negative returns.**   

# Access Dataset

Teams are provided with predictors and semi-annual returns for a group of stocks from `1996` to `2017`. This span of **21 years** is represented as **42 non-overlapping 6-month periods**. In each of the `42 time periods`, roughly **900 stocks** with the largest market capitalization (i.e., total market value in USD) were selected. Therefore, the selected set of stocks at each time period changes as companies increase or decrease in value. **All stock identifiers have been removed** and **all numeric variables have been anonymized and normalized**. Training and test datasets were created by selecting a **random sample of stocks** at each time period. `60%` of stocks were sampled into the training set and the remaining `40%` created the test set. Finally, all data from the second half of 2017 was allocated to the test set. This 6-month period will provide a final out-of-sample test of a model’s performance.

You can download the datasets at : [https://www.crowdai.org/challenges/ieee-investment-ranking-challenge/dataset_files](https://www.crowdai.org/challenges/ieee-investment-ranking-challenge/dataset_files)

# Problem Statement

Each team must create a model that ranks a set of stocks based on the expected return over a forward 6-month window. This model can be a risk factor-based strategy (multi-factor model), predictive model, or any other data-based heuristic. There are many ways to approach this task and creative, non-traditional solutions are strongly encouraged. The final model will be tested on each 6-month period from 2002 to 2017.

# Installation

```
git clone git@github.com:crowdAI/ieee_investment_ranking_challenge-starter-kit.git
cd ieee_investment_ranking_challenge-starter-kit
pip install -r requirements.txt
pip install --upgrade crowdai
```
**Note** : This challenge expects atleast `crowdai` client version `1.0.17`
You are then expected to go to the [Datasets Page](https://www.crowdai.org/challenges/ieee-investment-ranking-challenge/dataset_files)  and download the `Full Dataset` file and save it inside the `data/` folder as `full_dataset.csv`; and then download the `Prediction Template` file and save it inside the `data/` folder as `prediction_template.csv`.

# Baselines
A [jupyter-notebook](http://jupyter.org/) with instructions for parsing the data, training a simple random forest based model, and making a submission is available at : [random_forest.ipynb](random_forest.ipynb)

You should be able to access it by :
```
# Please Ensure that you have already completed the steps mentioned in the section `# Installation`.
jupyter-notebook random_forest.ipynb
```

# Submission of predicted file to crowdAI
```
import crowdai
api_key = "YOUR CROWDAI API KEY HERE"
challenge = crowdai.Challenge("IEEEInvestmentRankingChallenge", api_key)
result = challenge.submit("sample_submission.csv")
print(result)
```
**Note** : The evaluation script was incorrectly calculating NDCG as of the challenge launch. This was fixed 03/28. Solutions submitted prior to this date would have provided incorrect results. For details and questions, join the discussion [here.](https://www.crowdai.org/topics/notice-error-in-ndcg-calculation-in-evaluation-script/discussion)

# Author
SP Mohanty <sharada.mohanty@epfl.ch>   
Harlander, Benjamin <Harlander.Benjamin@principal.com>
