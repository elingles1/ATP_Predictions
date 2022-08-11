# Professional_Tennis_Predictions
By:
    Tom Smith and Eli Ingleson

## Business Understanding
People are always going to gamble on sports winners or at least try to predict the outcome. This project will be able to help people make smarter bets and more accurate predictions. By utilziing individual player statistics, we will be able to predict who wins matches and why they are able to do so.

## Business Problem
Our business problem was to identify aspects of a tennis match that lead to winning or losing and use these features to predict the winner of a professional match. This could be useful for gamblers as well as curious tennis fanatics.

## Data Understanding
We are getting our data from Jeff Sachman's github page "tennis-atp", which is linked here: https://github.com/JeffSackmann/tennis_atp. He has CSV's going all the way back to 1968 with recorded atp matches and their stats. However, we are only going to use data going back to 1991. This is because Jeff mentioned that some of the data was incomplete once you go past that threshold. This data is updated on a weekly basis and includes data on individual matches as well as player statistics such as height and age.

## Methods

Many of the columns in the original dataset were not needed for our models. Some of these columns included player height, which hand they used, and tournament id's. After we dropped many columns, we were only left with columns pertaining to who won or lost each match and their statistics for that one match.

We dropped our rows with nulls. Almost all of our null values were in columns pertaining to game statistics. We felt that it would be too inaccurate for us to try and fill these values with anything. 

The last step we took before we began our modeling process was to put everything in terms of favorite instead of winner or loser. We considered the favorite to be the higher ranked player, and we put everything in terms of whether the favorite won or not.

## Modeling

When we began the modeling process, we were down to 9 columns. Using these columns we ran a logistic regression, a decision tree, a random forest, and a Naive Bayes model. 

All of our models were in the 80-87% accuracy range. This was good to see as this is a good score and as it beat our model-less baseline of 64% accuracy.

## Final Model

For our final model, we chose our logisitic regression model. It had the highest score at 87% and had virtually no discrepancy between its train and test score.

To see how it accurate it really was, we input our holdout set which was all the matches past 2021. Our model was able to predict roughly 85% of these matches correctly.

## Website Predictor

Using our final model, we built a function where a user would input two players and a surface type. The function would then return who would win and the probability that they will win. We then created a website linked here: https://tennispredapp.herokuapp.com/

## Conclusion

According to our final model, we can predict the winner of a tennis match with roughly 85% accuracy. Furthermore, in our data, we found several trends that could be useful for predictions. The most strongly correlated feature with the outcome of a match is the number of break points a player faces in a match. The more break points they face, the higher the likelihood they lose. Similairly, the more points a player plays on their service game, the more likely they are to lose.

This project was very interesting and was something we both truly enjoyed working on. However, due to time constraints, we were unable to finish everything we wanted to do. The first thing we would like to do is increase our model's accuracy. Our model has no data on returns and return games, so if we could find data on that, we could potentially make our model more accurate.

It would also be beneficial for our model and website to automatically update our data as new matches are being played constantly. Another thing we would like to do is track player momentum by filtering recent matches and results. Players will have streaks of brilliance that allows them to beat players they would normally lose to and vice versa.

## Repo Navigation
```
├── data <- Data Folder.
├── Notebooks <- Working Notebooks.
├── License
├── Presentation <- Presentation Report
├── Final Notebook <- Report Notebook
├── README.md <- The top-level README for developers using this project.
```