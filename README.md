# **Amazon Vine: A PySpark Analysis**
## **Overview of the analysis**
The purpose of this project was to analyze Amazon reviews written by members of the paid Amazon Vine program. This program allows sellers to receive reviews for their products. 

The main objective that the project tried to achieve was to determine if there is any bias toward favorable reviews from those who have paid subscriptions to the Vine program. 

We performed this analysis with the use of the following tools:

1. Python
2. Google Colab
3. PySpark
4. PostgreSQL

## **Results**
The specific dataset that we analyzed related to products within the "Music" category (such as CD's, for example). The following questions give us a few clues to interpret the results: 
* How many Vine reviews and non-Vine reviews were there?

The *Music* dataset was one that had many more non-Vine reviews, compared to the Vine reviews. There where a total of **7** vine reviews, while the non-Vine reviews were **105,979**. Figures 1 and 2 show us the code that we used, as well as the output for each category. 

*Figure 1. Total vine reviews.*

*Figure 2. Total non-vine reviews.*

* How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

Within the paid Vine category, we found that none of the reviews were 5 starts. When it came to the non-Vine category, we calculated a total of **67,580** 5-star reviews. 

*Figure 3. Vine 5-star reviews.*

*Figure 4. Non-vine 5-star reviews*.


* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

When it came to the Vine reviews, we already knew that there would be a percentage of 0% for the 5-star reviews. However, we still calculated the percentage of reviews that belonged to other ratings. We found that **43%** of the reviews for this category were 3-star reviews, while the other **57%** belonged to 4-star reviews. 

*Figure 4. Paid Vine reviews distribution.*

Regarding the non-Vine category, we found that **64%** of the total reviews were 5-star reviews (for the rest of the percentages, please look at *Figure 5*).

*Figure 5. Non-Vine reviews distribution*

## **Summary**
The *Music* dataset certainly gave us interesting results, especially considering the difference between the amount of paid and unpaid Vine reviews. Now, our main question for this project was the following: *Is there any positivity bias for reviews in the Vine program?*

This question is not easy to answer, given that the dataset we used gave us very few Vine reviews. With the information that we have, we would say that there is more of a neutral bias for reviews in the program, given that we only had 3 and 4-star reviews. 

Now, when it comes to non-Vine reviews, we might be more inclined to say that there is a positivity bias there, as 64% of the total reviews were 5-star ones. 

Taking all of this into account, we believe that an additional analysis might help us get more information surrounding the Vine program. The analysis we propose would take a look into the star_rating and helpful_votes columns, in order to determine if 5-star reviews tend to be considered more helpful than the reviews with less stars. For this, we would use the groupBy() function on the "star_rating" column, and sum the number of votes per group. Then, we would calculate the total percentage on each category, in order to determine the distribution of helpful_votes for each rating. 