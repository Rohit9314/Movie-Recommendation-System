# Movie-Recommendation-System

This is the code for building a recommendation system based on the nearest neighbours model using collaborative filtering.

## Overview

There are basically 3 types of recommendation algorithms
* Content based filtering - Find Products with 'similar' attributes
* Collaborative filtering - Find Products liked by 'similar' users
* Association rules learning - Find complementary Products

This recommendation is however based on Collaborative filtering which uses easily captured user behaviour data. The rating data is represented using a matrix where users are along the rows and products are along the columns. Blank Cells represent the ratings for unseen products.

There are different methods to fill the blank cells like nearest neighbour model, latent factor analysis, etc. by using values which are already filled in rating matrix. However, we will use Neareset neighbour model which measures similarity of users using distance metrics.
For example:


|  | M1 | M2 | M3| M4 | M5 |
| :-----: | :-: | :-: |:-: |:-: |:-: |
| U1  | `3`  | `4`  | -  | -  | `5`  |
| U2  | 1  | -  | -  | -  | 3  |
| U3  | 4  | 4  | -  | 5  | 4  |
| U4  | `3`  | `5`  | 3  | 4  | `5`  |

Here user 1 has seen movies 1, 2, 5 but not 3 and 4. Our objective is to estimate the rating which the user can give to unrated movies and then we can sort the rating and select top 'N' movies liked by that user. 
### But how do we find the unrated ratings?
We can do this by finding the average of ratings given by other 'similar' users like user 4 has similar taste as of user 1 in the above table. So we can assign the rating 3 and 4 and if more than one similar user is present we can take the average and then assign it.

And to find the similar users we use K Nearest Neighbour model.

## Dependencies
* scipy
* pandas
* numpy
