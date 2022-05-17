# Module 4 Project


* Student name: **Will Dougherty**
* Student pace: **self paced**
* Scheduled project review date/time: **17 May 2022, 2:00-2:45 PM**

## Description

In this project I will be be building a recommendation system using the MovieLens dataset.

The overarching task is:

* Build a model that provides top 5 movie recommendations to a user, based on their ratings of other movies.

With this as the core objective, I will expand on this to create a framework for providing recommendations to existing users, as well as new users.

## Business Problem

FlixWeb is a relative newcomer to the online movie-streaming space. Their current platform provides films to users, who rate them, and then those ratings help users find quality films to watch.

However they've received lots of feedback requesting more personalized recommendations, since users often spend a lot of time looking for something to watch, and would like to have more tailored recommendations based on the ratings they've given to films.

* Better recommendations means more user engagement, and they'll be more likely to choose our service to give them interesting suggestions for what to watch.
* Users often want to watch 'something', maybe even with a general parameter in mind ('horror movie', 'classic film') but spend a long time in our app looking around before deciding on what to watch.

As the lead data scientist for FlixWeb, I am tasked with building a recommendation system for existing users. In addition, we need a way to recommend films to new users, and onboard them onto the service, leading to their user profile becoming 'mature' and able to be incorporated into the full model.

## Goals:

1) Since movie ratings are the raw material of the dataset, the model will predict users' ratings. However, the more important measure is how a user would rank a collection of films, as every user is rating films on their own subjective, un-scientific scale. Thus, I will target the highest NDCG (Normalized Discounted Cumulative Gain) across all users in order to maximize the quality of recommendations, as any list of recommended films is itself a predicted ranking.

2) Use these predictions to implement a framework for making recommendations. This will include basic 'Top 5' recommendations, as well as top films in a given genre or decade, and also films that are 'hidden gems' (few rankings).

3) Create a plan for providing recommendations for new users with few or no ratings, and onboard them until their user profile matures.

## Dataset and Methodology

* The MovieLens dataset comes in two sizes: the full set (> 27 million ratings) and a small set (> 100,000 ratings). I will perform EDA on the small set, and based on this, will decide how to either use that dataset, or subset the larger set.

* I will utilize an ALS collaborative filtering approach to build the main model, and will target NDCG to tune and optimize the model. Although I will measure RMSE to determine how closely the model predicts users' ratings, NDCG is a better measure of how accurate the predicted ranking of recommended films will be.

* I will also utilize content-based filtering to deal with cold-start (new) users, to recommend films based on the few films a user has already watched (before user profile completion).

* Finally, I will create a mockup that pulls all of this together, and simulates the user experience of a new user to the service. This will walk through the process of initial recommendations, early content-based filtering, completion of the user profile, and generation of collaborative-filtering recommendations.