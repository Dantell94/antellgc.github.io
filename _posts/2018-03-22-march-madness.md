---
published: true
---
## March Madness Tournament Predictions

An attempt to forecast the champion of the 2018 NCAA basketball tournament using machine learning. This entry was originally published on the [BigML blog](https://blog.bigml.com/2018/03/22/finding-sense-in-march-madness-with-machine-learning/). 

If you are one of the approximately 54 million Americans that filled out a bracket to predict the NCAA Men’s Basketball tournament this year, odds are that your bracket was no longer perfect within the first 24 hours of tournament, and substantially off track by the end of the opening weekend. Correctly predicting all 63 games (ignoring the 4 play-in games) is infamously difficult, with a probability that ranges from 1 in 9.2 quintillion to a much more manageable 1 in 128 billion, depending on who is counting. With such low odds, it is no surprise that Warren Buffet had famously offered a $1 billion prize to anyone who correctly picks every winner.

Not familiar with how the NCAA basketball tournament works? Now is a good time to pause and check out this guide.

This year, the tournament once again lived up to its “March Madness” moniker with a number of heavy favorites losing in the first two rounds of the tournament. The chaos was headlined by an unprecedented upset of #1 overall seed Virginia in the first round by long shot UMBC, and also claimed #1 Xavier, #2 North Carolina, and #2 Cincinnati as victims. With so many brackets officially busted, we decided to investigate how a Machine Learning approach would perform on predicting the remainder of the tournament.

### Data Collection and Feature Engineering

In nearly all data analysis projects, data acquisition and wrangling constitute the greatest challenge and time demand. Fortunately, a well-structured data set of NCAA basketball games  – extending back to the 1985 season – has been compiled by Kaggle and Kenneth Massey. While this data was not in a format that could be considered “Machine Learning-ready” it did provide substantial raw material to engineer features. Our approach was to represent each team as a list of these engineered features, such that each past basketball game could be represented by the combination of two lists (one for each team), and an objective field consisting of the result of the game from the perspective of the first team listed. Because so many of our features relied on data that was only collected going back to the 2003 season, we limited our final data set to 118 total features acquired from the most recent 15 seasons.

The features used in this investigation belonged to several different categories:
* Team performance: e.g., home/away wins, wins in close games, longest win streak, scoring differential, etc.
* In-game statistics: e.g., free-throw percentage, three-point field goal percentage, average three-point field goal attempts, average rebounding difference, etc.
* Ranking information: e.g., RPI, tournament seeding, Whitlock, Pomeroy, Sagarin, etc.
