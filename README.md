# Skouppi = Scope + Skuuppi
## Topic-based News Collector with serverless AWS resources

The application searches through predefined rss-feeds for news items and collects all the news items relevant to the topic defined when creating an AWS Comprehend custom classification model. AWS Comprehend is a natural-language processing (NLP) service that uses machine learning to uncover valuable insights and connections in text.

Custom classification model can be switched in the program as needed.

This program is designed to run on AWS serverless resources (Lambda, s3 etc.) and can be deployed with the Serverless framework template.

### RSS-Lambda
A Lambda function that collects news items from various RSS feeds according to a predefined feed.json and launches a custom AWS Comprehend classification job.  A news item is compared to the custom model, and is given a score according to that comparison.


### Dataggregator-Lambda
A Lambda function uses those scores to classify news items according to previously launched AWS Comprehend classification job and after that produces and a file with the relevant news items.


### Api-Lambda
A Lambda function for running API access service providing the final output, all the news items that match the original custom model.


### Example
Example of JSON output (one news item) from API. 

![image](https://user-images.githubusercontent.com/56840557/188081538-371ca5ec-2acf-4273-ae88-bcfb0af72063.png)

