# Project: Disney Movies and Box Office Success


<p align="center">
  <img width="700" height="900" src="https://user-images.githubusercontent.com/67468718/104902958-3f4b4100-5934-11eb-8190-fed8a44f7f2b.JPG">
</p>


## Introduction
Walt Disney Studios is the foundation on which The Walt Disney Company was built. The Studios has produced more than 600 films since their debut film, Snow White and the Seven Dwarfs in 1937. While many of its films were big hits, some of them were not.

## Objective

In this project:
  * We will analyze data to see how Disney movies have changed in popularity since its first movie release
  * Also we will perform hypothesis testing to see what aspects of a movie contribute to its success. 
  
## Dataset

The dataset used in this project is a modified version of the Disney Character Success dataset from <a href="https://data.world/kgarrett/disney-character-success-00-16">Kelly Garrett</a>

The data contains 579 Disney movies with six features: movie title, release date, genre, MPAA rating, total gross, and inflation-adjusted gross.  

## Visualize the genre popularity trend:

The line plot supports our belief that some genres are growing faster in popularity than others. For Disney movies, Action and Adventure genres are growing the fastest. 

![genre](https://user-images.githubusercontent.com/67468718/104915243-39aa2700-5945-11eb-9868-a14d729ce5b3.JPG)

## Data Transformation

we will build a linear regression model to understand the relationship between genre and box office gross. Since linear regression requires numerical variables and the genre variable is a categorical variable, we'll use a technique called one-hot encoding to convert the categorical variables to numerical. This technique transforms each category value into a new column and assigns a 1 or 0 to the column.

For this dataset, there will be 11 dummy variables, one for each genre except the action genre which we will use as a baseline. For example, if a movie is an adventure movie, like The Lion King, the adventure variable will be 1 and other dummy variables will be 0. Since the action genre is our baseline, if a movie is an action movie, such as The Avengers, all dummy variables will be 0.

## The genre effect (Regression Model):

Now that we have dummy variables, we can build a linear regression model to predict the adjusted gross using these dummy variables.

From the regression model, we can check the effect of each genre by looking at its coefficient given in units of box office gross dollars. We will focus on the impact of action and adventure genres here. (Note that the intercept and the first coefficient values represent the effect of action and adventure genres respectively). We expect that movies like the Lion King or Star Wars would perform better for box office.

## Confidence intervals for regression parameters:

  * We will calculate the confidence intervals using the pairs bootstrap method: we will compute 95% confidence intervals for the intercept and coefficients. The 95% confidence intervals for the intercept a and coefficient bi means that the intervals have a probability of 95% to contain the true value a and coefficient bi respectively. If there is a significant relationship between a given genre and the adjusted gross, the confidence interval of its coefficient should exclude 0.
  
  * After the initialization, we will perform pair bootstrap estimates for the regression parameters. Note that we will draw a sample from a set of (genre, adjusted gross) data where the genre is the original genre variable. We will perform one-hot encoding after that.
  
  * We compute 95% confidence intervals for the intercept and coefficient and examine if they exclude 0. If one of them (or both) does, then it is unlikely that the value is 0 and we can conclude that there is a significant relationship between that genre and the adjusted gross.
  
## Summary and Conclusion: 

Should Disney make more action and adventure movies?

The confidence intervals from the bootstrap method for the intercept and coefficient do not contain the value zero, as we have already seen that lower and upper bounds of both confidence intervals are positive. These tell us that it is likely that the adjusted gross is significantly correlated with the action and adventure genres.

From the results of the bootstrap analysis and the trend plot we have done earlier, we could say that Disney movies with plots that fit into the action and adventure genre, according to our data, tend to do better in terms of adjusted gross than other genres. So we could expect more Marvel, Star Wars, and live-action movies in the upcoming years!







