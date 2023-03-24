# mkt_promition_optimization
Team members:
- Lulu Xingchen Wang
- Lydia Jiarui Cao
- Han Jiang
- Sam Zihao Ding


## Project Statemetn
Our (hypothetical) client is WrestleNetUSA (WNU) - a professional wrestling company who is attempting to acquire subscribers for their online streaming platform. The company was founded in 2010, and has routinely used targeted tiered promotional packages to incentivize individuals identified by analytical models to subscribe or purchase other company offerings.

WNU has identified a list of potential subscribers who, according to internal models, are highly unlikely to organically subscribe to the streaming platform. In order to expand their customer base, WNU wants to run a new targeted promotion campaign for this list of customers. 

The company has 3 promotional tiers for the online streaming platform to offer these customers: Bronze, Silver and Gold. These promotional tiers offer free content for subscribers to incentivize sign-ups. These tiers cost WNU $500, $1100 and $1400 to offer, respectively.

Our goal is to:
-  determine which individuals in the validation dataset should we offer promotional tiers to, and which promotional tier should be offered to these individuals
- For simplicity, there are no budget constraints, but the company’s goal is maximizing its profit; but incoporating budget constraint is a plus
- For the purposes of this exercise, we can assume that any customer who is not offered a promotion will not subscribe, and thus has an LTV and acquisition cost of $0.

## Methodology

For data preprocessing and EDA, we followed a normal approach: checking distributions, correlation, extreme values, outliers, etc. Findings were used for feature engineering and feature selection (RFE). 

For modeling, we designed a two-fold prediction model, which firstly made prediction on life-time-value (LTV) via lightGBM regressor and secondly use GLM method (logistic regression) to predict the probability on whether the user would subscribe if provided bronze/silver/gold promotions (respectively). With this approach, we can estimate whether a user will be converted (aka. subscribe to our services) and how much LTV they will generate to the company.

Based on the life-time-value and promotion cost of each user, we can calculate the profit. Although we werer allowed to make the assumption that there's no budget limit, we still provided an optimization approach to add promotion budget when making the final approval of our promotion offers. By doing so, we brought this project closer to real-world scenario with budget simulation.

