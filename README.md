# Sentiment-Analysis

#using newspaper3k library for extracting articles
from newspaper import Article

url = 'https://apnews.com/article/uvalde-texas-school-shooting-44a7cfb990feaa6ffe482483df6e4683'

# Creating an object Article and passing url as a parameter and then downloading and parsing the file
article = Article(url)

article.download()
article.parse()
article.nlp()

import string

text= article.text

print(text)
# Changing the text to all lower cases
lower_case= text.lower()

# Cleaning Text steps 
# 1- Create text file and take text from it
# 2- Convert the letter into lowercase 
# 3- remove puntuations like ., !? etc.

# Removing all the puntuation marks in the text
cleaned_text=lower_case.translate(str.maketrans('','',string.punctuation))

# str1= specifies the list of characters that need to be replaced
# str2= specifies the list of the characters with which the characters have to be replaced
# str3= specifies the list of the characters that need to be deleted
# returns the translation table which specifies the conversions that can be used by maketrans method
# maketrans method takes 3 parameters 
print(cleaned_text)

# tokenization of text : 
tokenized_text=cleaned_text.split()
print(tokenized_text)
