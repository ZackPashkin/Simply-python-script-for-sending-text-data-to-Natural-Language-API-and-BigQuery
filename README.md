# Simply-python-script-for-sending-text-data-to-Natural-Language-API-and-BigQuery
What is it good for? 
1. Sending the text data to the Natural Language API 
2. Classifying articles 
3. Importing articles to BigQuery


To run the following script:

**python classify-text.py**



**What script is actually doing:**

We're using the google-cloud Python client library to access Cloud Storage, the Natural Language API, and BigQuery. . When classifying each article is done, the data is inserted into BigQuery using insert_rows().

First, a client is created for each service.
Then references are created to the BigQuery table.
files is a reference to each of the dataset files in the public bucket.
We iterate through these files, download the articles as strings, and send each one to the Natural Language API in our classify_text function.
For all articles where the Natural Language API returns a category, the article and its category data are saved to a rows_for_bq list.
When classifying each article is done, the data is inserted into BigQuery using insert_rows().
Note: The Natural Language API can return more than one category for a document, but for this script you're only storing the first category returned, to keep things simple.

Enjoy the script!
