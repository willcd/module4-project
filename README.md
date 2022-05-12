# Module 4 Project


* Student name: **Will Dougherty**
* Student pace: **self paced**
* Scheduled project review date/time: **16 May 2022, 3:00-3:45 PM**

## Description

In this project I will be be building a recommendation system using the MovieLens dataset.

The overarching task is:

* Build a model that provides top 5 movie recommendations to a user, based on their ratings of other movies.

With this as the core objective, I will also create a framework for building user profiles (getting their movie ratings) that can then be used in the model to generate recommendations for the user.

## Business Problem

FlixWeb is a relative newcomer to the online movie-streaming space. After already being in service and providing movies to stream to thousands of users, and collecting ratings, they want to improve their recommmendation service, to re-position themselves as the go-to service for excellent, user-specific recommendations.

As the lead data scientist for FlixWeb, I am tasked with building a rating-prediction model using their already-large dataset of user ratings, which= can provide quality recommendations to existing users. In addition, we need a way to recommend films to new users, and onboard them onto the service, leading to their user profile becoming 'mature' and able to be incorporated into the full model.

### Goals:

1) Since movie ratings are the raw material of the dataset, the model will do its best to predict users' ratings. However, the more important measure is how a user would rank a collection of films, as every user is rating films on their own subjective, un-scientific scale. Thus, I will target the highest NDCG (Normalized Discounted Cumulative Gain) across all users in order to maximize the quality of recommendations, as any list of recommended films is itself a predicted ranking.

2) Use these predictions to implement a framework for making recommendations on two levels: a basic, 'best' recommendation list using all films; and a variety of ways to subset this, depending on what a user wants to see (genre, decade, etc).

3) Create a plan for providing services for new users with no ratings, and onboarding them as their user profile matures.

## Dataset and Methodology

* The MovieLens dataset comes in two sizes: the full set (> 27 million ratings) and a small set (> 100,000 ratings). I will perform EDA on the small set, and based on this, will decide how to either use that dataset, or subset the larger set.

* I will utilize an ALS collaborative filtering approach to build the main model, and will target NDCG to tune and optimize the model. Although I will measure RMSE to determine how closely the model predicts users' ratings, NDCG is a better measure of how accurate the predicted ranking of recommended films will be.

* I will also utilize content-based filtering to deal with cold-start (new) users, to recommend films based on the few films a user has already watched (before user profile completion).

* Finally, I will create a mockup that pulls all of this together, and simulates the user experience of a new user to the service. This will walk through the process of initial recommendations, early content-based filtering, completion of the user profile, and generation of collaborative-filtering recommendations.