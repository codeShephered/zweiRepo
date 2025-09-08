# API Iink into json
import requests
api_url = "https://www.wolframcloud.com/obj/raghuinfobits/percent-api?numQuestions=10&difficulty=medium" # Example API endpoint
response = requests.get(api_url)
data = response.json()
print("API Response Data:")
print(data)
# Json into df csv
import pandas as pd
df = pd.json_normalize(data) # For nested JSON
df.to_csv('output.csv', index=False) # index=False prevents writing DataFrame index
# CSV connecting to db
