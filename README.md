### ENTER YOUR NAME : Meiyarasi V
### ENTER YOUR REGISTER NO : 212221230058 
### DATE:12.05.2024
## Project Based Experiment
### Objective:
Perform sentiment analysis using your Facebook data and count the number of Occurrences of my name in the extracted text.
### Program:
~~~
pip install pandas textblob
import pandas as pd
from textblob import TextBlob

# Load the CSV file into a DataFrame
df = pd.read_csv('fb_sentiment.csv')

# Function to perform sentiment analysis using TextBlob
def analyze_sentiment(text):
    blob = TextBlob(str(text))
    return blob.sentiment.polarity

# Apply sentiment analysis to each row in the DataFrame
df['Sentiment'] = df['FBPost'].apply(analyze_sentiment)

# Output the DataFrame with sentiment analysis results
print(df.head())

# Filter out rows with negative sentiment (label 'N')
negative_feedback = df[df['Label'] == 'N']

# Output the negative feedback
print(negative_feedback)

~~~
### Output:
![image](https://github.com/21005984/Project-Based-Experiment-AAI/assets/94748389/c48c1b7a-27f2-4ee7-ba81-ba102168d553)

Inference:
Thus sentiment analysis using your Facebook data ias done and filtering the data that has only negative feedback for the code is done.
