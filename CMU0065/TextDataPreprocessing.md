#Tokenization
import nltk
nltk.download('punkt')
from nltk import word_tokenize, sent_tokenize
data = "This is a cat. It's so cute! "
result_sent_tokenized = sent_tokenize(data)
print(result_sent_tokenized)

result_word_tokenized = word_tokenize(data)
print(result_word_tokenized)

##### [nltk_data] Downloading package punkt to /root/nltk_data...
##### [nltk_data]   Unzipping tokenizers/punkt.zip.
##### ['This is a cat.', "It's so cute!"]
##### ['This', 'is', 'a', 'cat', '.', 'It', "'s", 'so', 'cute', '!']


text= ["An introduction to text analysis.", "This's a good example of text analysis!",
       "I am interested in NLP.","Machine learning is very interesting.",
       "Python is the best tool. I like it"]
#convert list to data frame
import pandas as pd
data = pd.DataFrame({'Text':text})
print(data)
 
#####  Text
#####         An introduction to text analysis.
#####   This's a good example of text analysis!
#####                   I am interested in NLP.
#####     Machine learning is very interesting.
#####        Python is the best tool. I like it

data['Text'] = data['Text'].apply(lambda x :"".join([w.lower() for w in x ]))
print(data)

  Text
0        an introduction to text analysis.
1  this's a good example of text analysis!
2                  i am interested in nlp.
3    machine learning is very interesting.
4       python is the best tool. i like it

#Text Nomalization
data_Stemming_pt=data.copy()
print(data_Stemming_pt)
data_Stemming_sn = data.copy()
print(data_Stemming_sn)
data_Lemna_nltk = data.copy()
print(data_Lemna_nltk)
data_Lemna_textblob = data.copy()
data_Lemna_spacy = data.copy()
print(data_Lemna_spacy)

#Text Nomalization
data_Stemming_pt=data.copy()
print(data_Stemming_pt)
data_Stemming_sn = data.copy()
print(data_Stemming_sn)
data_Lemna_nltk = data.copy()
print(data_Lemna_nltk)
data_Lemna_spacy = data.copy()


   Text
0        an introduction to text analysis.
1  this's a good example of text analysis!
2                  i am interested in nlp.
3    machine learning is very interesting.
4       python is the best tool. i like it
                                      Text
0        an introduction to text analysis.
1  this's a good example of text analysis!
2                  i am interested in nlp.
3    machine learning is very interesting.
4       python is the best tool. i like it
                                      Text
0        an introduction to text analysis.
1  this's a good example of text analysis!
2                  i am interested in nlp.
3    machine learning is very interesting.
4       python is the best tool. i like it
                                      Text
0        an introduction to text analysis.
1  this's a good example of text analysis!
2                  i am interested in nlp.
3    machine learning is very interesting.
4       python is the best tool. i like it


from nltk.stem import PorterStemmer
st =PorterStemmer()
data_Stemming_pt ['Text'] = data_Stemming_pt['Text'].apply(lambda x:" ".join([st.stem(w)for w in word_tokenize(x)]))
print(data_Stemming_pt)

 Text
0          an introduct to text analysi .
1  thi 's a good exampl of text analysi !
2                  i am interest in nlp .
3         machin learn is veri interest .
4     python is the best tool . i like it





