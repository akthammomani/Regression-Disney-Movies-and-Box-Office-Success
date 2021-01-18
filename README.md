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


