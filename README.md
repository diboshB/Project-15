# Project-15
Captsone_Project - Clustering - Review Rating


Analyzing Customer Sentiments and Clustering Reviews from
TripAdvisor
Problem Statement: This analysis aims to cluster customer reviews from
TripAdvisor into different themes based on the review text, which will help
identify what customers are liking and disliking. By clustering reviews,
businesses can gain insights into customer sentiment, which can inform
strategies to improve services, optimize customer experiences, and drive
business growth. Additionally, we explore how clustering models can be
applied to automatically cluster new reviews in the future.
Solution Approach: The solution is built around a series of key steps:
1. Text Data Cleaning:
o The raw text data from the review_full column contains special
characters, URLs, numbers, and unnecessary whitespaces. The
first step is to clean the text for better analysis.
Steps involved:
§ Remove URLs and special characters.
§ Convert all text to lowercase to ensure uniformity.
§ Tokenize the reviews to break them into words and remove
stop words (common words like "and", "the" that don't add
significant meaning).
2. Feature Extraction from Text Data:
o Once the reviews are cleaned, we use TF-IDF (Term Frequency-
Inverse Document Frequency) vectorization to transform the
text into numerical data, which can then be processed by
clustering algorithms. TF-IDF helps emphasize important words
while downplaying frequently used but less informative terms.
o TF-IDF Vectorizer:
§ Stop words are removed using the built-in stop word list.
§ The matrix created by the vectorizer represents each review
as a vector of numerical values indicating the importance of
each word in the review relative to the entire dataset.
3. Clustering of Reviews:
o After feature extraction, we apply K-Means clustering to group
the reviews into distinct clusters. K-Means is an unsupervised
machine learning algorithm that finds natural groupings within the
data.
o Determining the optimal number of clusters:
§ We use the Elbow Method to determine the optimal
number of clusters by plotting the Within-Cluster Sum of
Squares (WCSS) for different values of k. The elbow in the
graph indicates the point where increasing the number of
clusters no longer significantly reduces the WCSS.
o Based on the analysis, we chose 4 clusters for this dataset, which
were analyzed in detail later.
4. Assigning Meaningful Labels to Clusters:
o After the reviews are clustered, we examine the top words in each
cluster to understand the common themes. These themes are
used to label the clusters meaningfully.
o Cluster Labels:
§ Cluster 0: "Mixed Experience with Room for Improvement"
§ Cluster 1: "Highly Positive Dining Experience"
§ Cluster 2: "Dish-Specific Reviews with Some Dissatisfaction"
§ Cluster 3: "Outstanding Experience with Excellent Service"
5. Sentiment Analysis:
o Sentiment analysis is performed on each review to categorize
them as "positive", "negative", or "neutral". The TextBlob library
is used to calculate the sentiment polarity score of each review.
o Reviews with a positive sentiment have a polarity score greater
than 0, negative reviews have a polarity score less than 0, and
neutral reviews have a score of 0.
o The sentiment distribution is analyzed within each cluster to
understand how sentiment varies across different themes.
6. Visualizations:
o Sentiment Distribution by Cluster: A bar plot is generated to
visualize the distribution of positive, negative, and neutral
sentiments across the different clusters.
o Top Words in Positive and Negative Reviews: For each
cluster, we extract and display the most frequent words in both
positive and negative reviews to identify the key aspects
customers are commenting on (e.g., service quality, food taste).
o Custom Color Palette for Sentiment Visualization: A
customized color palette (green for positive, red for negative, and
gray for neutral) is used to make the sentiment distribution
clearer.
Key Insights:
• Cluster 0 (Mixed Experience with Room for Improvement):
o Top Words: "food", "place", "restaurant", "service", "staff".
o Sentiment: Mostly positive reviews with a significant number of
negative reviews. Customers appreciate the food and place but
highlight areas for improvement in service and staff interactions.
• Cluster 1 (Highly Positive Dining Experience):
o Top Words: "good", "food", "service", "place", "restaurant".
o Sentiment: Largely positive sentiment. Customers are highly
satisfied with the food, service, and ambiance of the restaurant.
• Cluster 2 (Dish-Specific Reviews with Some Dissatisfaction):
o Top Words: "chicken", "butter", "food", "place", "tikka".
o Sentiment: Reviews are mostly positive but with some negative
comments related to specific dishes, such as "chicken" and "butter
chicken".
• Cluster 3 (Outstanding Experience with Excellent Service):
o Top Words: "great", "food", "service", "ambience", "staff".
o Sentiment: Predominantly positive reviews, highlighting
excellent food, service, and overall experience.
Top Positive and Negative Themes:
• Positive Themes:
o "Good food", "great service", "pleasant ambiance", "friendly staff",
and "authentic Indian cuisine".
• Negative Themes:
o "Slow service", "poor customer support", "staff issues", "bad
experience with specific dishes".
Future Application for New Reviews:
• The clustering model developed can be used to automatically categorize
new reviews as they come in. By maintaining and updating the model
with new data, the system can continuously learn and assign reviews to
appropriate clusters.
• Automated categorization will save businesses time and effort in
manually analyzing reviews. It will also provide real-time insights into
customer satisfaction, helping businesses respond proactively to
emerging issues.
Conclusion:
This analysis successfully clusters TripAdvisor reviews into meaningful themes
and performs sentiment analysis to understand the underlying customer
sentiments. By identifying common themes in customer reviews, businesses
can improve their offerings and services. The insights derived from positive
and negative themes can drive targeted improvements in customer
experience. Additionally, the clustering model provides a foundation for
automatic categorization of future reviews, ensuring scalability and efficiency
in handling large volumes of customer feedback.
