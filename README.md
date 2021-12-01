# Erdos_RootInsurance_FinalProject_2021
Repository for Erdos Institute Root Insurance Final Project 2021 Group Koala

Group Members:
Wendson Antonio de Sa Barbosa,
Preston Pozderac,
David Wen

This project is a requirement of completeion for the Fall 2021 Data Science Bootcamp at the Erdos Institute.
This is a corporate sponsered project by Root Insurance. 

Project Description https://drive.google.com/file/d/1o1VlpVhNBgW8RQC9C2wKxRg_N28uQXPv/view?usp=sharing

## Project Overview:

The ACME Insurance Company is assessing its marketing spending on a vertical search channel.
A customer will enter infromation about their insurance needs, and insurance companies will place a bid for the customer.
Ads are then displayed in order of highest to lowest bids for the customer from rank 1 to 5.
When a customer clicks on the ad, the company pays the price of their bid and the customer is then able to purchase a policy. 


## Project Goal:

Determine a bidding strategy, based on the type of customer, that will optimize the cost per policy sold while ensuring that 400 policies are sold per 10,000 ads.

## Dataset

Our data set consists of 10,000 ads with the 4 customer features ("Insurance Status", "Number of Drivers", "Number of Vehicles", and "Marital Status") and the 3 website features ("Rank", "Clicks", and "Policies Sold"). The final variable is the "Bid" which was a constant $10 for all 36 customer demographics. Since it was constant, we can not include it in any of our models. From the 10,000 impressions, 1878 produced clicks and 783 policies sold. This imbalanced data was combatted using various sampling techniques as well as stratification on our testing and training data. 


Note: This means our original bidding strategy exceeds the goal of 400 policies sold per 10,000 customers however we will  still look to optimize the cost per policy. 


## Approach

We developed three models to predict the key output variables of: Ad Rank, Number of Clicks, and Policies Sold.
Since the variable bid cannot be implemented in the model, each model provides crucial information for determining the optimal strategy.

Rank: Determines which customers demographics our initial $10 bid under and over performs on. When it underperforms, we know other companies value these customers and are consistently outbidding us. 

Clicks: Evaluates the overall cost of each demographic as companies only pay their bid if a customer clicks. Important in order to minimize our cost per policy. 

Policies Sold: Predicts the total policies sold within each demographic and how changes in rank can affect sales. This allows us to find which customers represent the greatest market for potential growth through increased bids.

### Rank Model
[Rank Model link](RootProject_RandomForest_FinalModel.ipynb)

The rank model uses a random forest model and the features of "Insurance Status", "Number of Drivers", and "Number of Vehicles" to determine the probability distribution of ranks 1-5. Different models were compared using the area under the receiver operating characteristic curve using both "one vs one" multi-class classification. The accuracy of this model 0.43 as opposed to the baseline accuracy (always chose the median/mode rank of 3) of 0.24. From the importance score, the "Insurance States" is the most significant (0.627), nearly double the "Number of Vehicles" (0.336), with the "Number of Drivers" has only a marginal effect (0.037). This follows EDA as there is a stark difference between "Unknown" insurance status and the "Yes" and "No" classes, followed by smaller changes based on number of vehicles.

### Clicks Model
[Clicks Model Link](Model%20-%20Clicks%2C%20Neural%20Network.ipynb)

### Sales Model
[Sales](Model%20-%20Policies%20Sold%2C%20Logistic%20Regression.ipynb)

## Results

## Bidding Strategy

## Future Iterations
