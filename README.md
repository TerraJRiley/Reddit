# Reddit
## Abstract
How many times have you opened up a browser for a random subreddit only to find that it wasn't the random subreddit you were looking for? We've all been there. Furthermore, what about when you wonder "golly, just how similar are different subreddits that are focused one concept but from entirely different points of view?" Well, we hear you. We've scrapped data from two active subreddits which focus around sexuality and using them build a model that's able to detect if it's one subreddit or the other with over an 80% certainty. Furthermore, if future exploritory data analysis, we hope to one day be able to talk about the defining features of each subculter that's being represented by these subreddits.  This started as a project for DSI, now further developed into it's own explorative project.

## Problem Statement
The original objective was to select two reddit forums and build a model that could identify when a post was made in one forum or another.  This project was also used at the time as a way to practice using the requests library, handling NLP and running models on documents.

## Data Collection
Data was collected via the Reddit API.  The original posts were collected on the date 9/09/2018.  
Post graduation of G.A.'s Data Science Intensive I (Terra Riley) have started collecting data starting on the date 10/29/2018 (which is erroniously labeled as 10_30 in places as of the time of this writing) from a larger pool of subreddits.
    
## EDA
By looking at words most correlated to one subreddit or the other we can infer what these forums have most different from eachother. Some of which were obvious, such as words being associated with sexuality having a high correlation to the lesbian forum, but others are more odd, like how the use of words like "month", "time", "week" and "ago" seeming to point to a higher mention of recent or future timeframes when compaired to the incels. For the incels this seems to have sifted those words around thier specific ingroup terminology such as "chad", "oneitis" and "blackpill".
    
## Modeling & Results
Original modeling utilized a random forest classifier and a multinomial Neïve Bayes Classifier.  Later, I was interested modeling with a number of different models.  The following is a list of the models used.  This was without any gridsearching.

|Model                  | Train             |Test               |
|-----------------------|-------------------|-------------------|
|Multinomial Neïve Bayes|0.9263513513513514 |0.8663967611336032 |
|Logistic Regression    |0.977027027027027  |0.8421052631578947 |
|Extra Trees            |0.9898648648648649 |0.8016194331983806 |
|Gradient Boost         |0.8722972972972973 |0.7975708502024291 |
|K Nearest Neighbors    |0.7763513513513514 |0.6497975708502024 |
|Support Vector Machine |0.6054054054054054 |0.6376518218623481 |

This is more of a statement about where I was with my modeling skills of the time than how similar the lesbians and incels subreddits are.  To do this we would need to have another model with other subreddits to compair them with.  
Logistic regression model being the second best is reassuring because it's the easiest to obtain insights with.  
    
## Future Steps
 - Finish setting up a class for the reddit data such that one can easily gather data on any subreddit that they're interested in.
 - Compare results and EDA of various subreddits based on sexaulity and gender
