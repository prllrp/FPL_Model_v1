# FPL_Model_v1

This repository contains my first attempt at using Machine Learning to predict player performance in Fantasy Premier League. 

## Introduction
Fantasy Premier League  is a fantasy soccer league based on the English Premier League. Every week fantasy managers pick a team of real players and are awarded points based on their perfomance. 
Soccer is unique in that impactful events (goals) are very infrequent and varied when compared to sports like baseball or basketball. This makes it a ripe field for machine learning as there are few linear relationships between publicly available data.
This repo serves as an attempt to train a Mulitlayer Perceptron (MLP) Classifier on a dataset compiled of data publicly available from Github and Understat.com. The performance of the team selected by this model will be shared below at the end of the 2023/24 season.

## Data
Fantasy Premier League data for  the 2022/23 season  was obtained from the Github repo: https://github.com/vaastav/Fantasy-Premier-League. Player and Team data for the 2022/23 season was scraped from Understat.com. These dataset was combined in to a single dataset with 22 parameters accounting for the players previous years performance, their teams previous years performance, and their opponents previous year performance. 
The training set included every player for every gameweek of the previous season that averaged more than 60 minutes per game and had corresponding data on Understat.

## The Model
There is a low degree of correlation between much of the data obtained and the amount of total fantasy points a player scores every week. This is because total points are mainly influenced by infrequent actions (goal sccoring and assists). 
One metric that has a high correlation with total points is the Bonus Points System. The Bonus Points System takes in other statistics to determine which players performed the best and should recieve bonus points. The BPS points has a higher correlation with the data obtained to this was used as a proxy for total points and set as the target for our model.
The model consisted of a Multilayer Perceptron Classifer (MLP) with 1500 nodes and three layers with a ReLu activation function. 22 parameters of player, team and opposition stats were used to predict whether a player against a given opponent would be in a given quantile of BPSS points.  

## Results
The model was scored with a test data set at r^2: 0.722 and Loss: 0.5710. The model was used to predict at multiple different quantiles above 70% and the players who were most commonly predicted to be included in the quantile over the next five gameweeks were selected to form a team.
The squad selected for the start of the 2023/24 season is as follows:


GK: Andre Onana, Fraser  Forster


DEF: Trent Alexander Arnold, Kieran Trippier, Antonee Robinson, Luke Shaw, Ezri Konsa


MID: Bruno Fernandes, Martin Odegaard, Pascal Gross, Douglas Luiz, Bryan Mbeumo


FWD: Harry Kane, Ollie Watkins, Yoane Wissa 
