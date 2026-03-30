# Natural Language Processing

<p align="justify">
Natural Language Processing (NLP) refers to the methodologies and complexity employed on computers to understand human language called "natural language" such ambiguity, polysemous words or irony. Trought its development, different techniques have led to the current <b> Large Language Moldes (LLMs) </b>. The initial favorable outcomes employed language rules and <b>One-Hot vectors</b>, therefore integrating different approaches within <b>Neural Network</b> connections and finally adding an <b>attention layer</b> to figure out the most important correlations between words.
</p>

## Summary

- The Beginning
- Preprocessing Techniques
- Natural Language Processing
  - $${\color{orange}Bag \space of \space Words \space (Bow)}$$
  - $${\color{orange}Term \space Frequency \space - \space Inverse \space Document \space Frequency \space (TF-IDF)}$$
  - $${\color{orange}Language \space Models}$$
      - $${\color{lightskyblue}N-Grams}$$
  - $${\color{orange}Word2Vec}$$   
      - $${\color{lightskyblue}Neural \space Networks}$$
      - $${\color{lightskyblue}Continuous \space Bag \space of \space Words \space(CBOW)}$$
      - $${\color{lightskyblue}Skip-Gram}$$
  - $${\color{orange}Transformers}$$   
      - $${\color{lightskyblue}Seq2Seq \space (Encoder \space - \space Decoder)}$$
- Video

# The Beginning

<p align="justify">
The start of natural language processing relates during cold war where translation of Russian military documents, papers and literacy was essential to the United States to keep up to date. On <b>January 7th, 1954</b>, at IBM the university of Georgetown built the experiment of <b>"Georgetown-IBM"</b> making use of prepared selected phrases to enhance results, nevertheless outside those sentences the model struggle of to capture context then leading to an investment cease in research.
</p>

<p align="justify">
Eliza was the <b>first natural language processing program released in 1966 by Joseph Weizenbaum</b> employing basic query consults in a database and adding basic language rules, result into the initial favorable outcomes tricking people on the time to think they were talking with a human being instead of a machine, thriving the Turing test.
</p>

```
Human: My boyfriend made me come.
ELIZA: Your boyfriend made you come?
Human: He says I'm depressed most of the time.
ELIZA: I’m sorry to hear that you are depressed.
Human: It’s true. I am unhappy.
ELIZA: Do you think coming here will help you not be unhappy?
``` 

<p align="center">
  <em>“Can machines think? I believe to be too meaningless to deserve discussion.”</em><br>
  <strong>— Alan Turing</strong>
</p>

# Preprocessing Techniques

<p align="justify">
The complexity of natural language processing relies on <b>giving a reliable numeric representation called embedding</b>, to easily overcome this issue preprocessing techniques are applied after segmenting text into individual words named "tokens". A successful tokenization process should be able to adjust and clean the data, disjoin punctuation marks and break off grammar.
</p>

- **Stemming:** Deletes word suffixes.
- **Lemmatization:** Removes word affixes returning an standard normalized version.

>[!NOTE]
> Both teniques reduced word sparcity by substracting word derivation and therefore shiriking dimmensions. Search Engines applied this techniques to improve results quality.

## Examples

| Original Word | Stemming | Lemmatization |
|--------------|----------|---------------|
| running      | run      | run           |
| studies      | studi    | study         |
| better       | better   | good          |
| leaves       | leav     | leave         |
| cars         | car      | car           |
| went         | went     | go            |
| flying       | fli      | fly           |
| happiness    | happi    | happy         |
| cats         | cat      | cat           |
| playing      | play     | play          |

>[!IMPORTANT]
> Stemming has a lower computer complexity, however its results are not guaranteed to be good enough, struggling at words that dramatically change their structure after verb conjugation such verb to be. On the other hand, Lemmatization makes use of more computational power to archive its result.

## Stop Words

<p align="justify">
Natural language is prone to be saturated with articles and connectors which give structure and sense to sentences, however they do not present additional information, these "stop words" are recommend to be removed when facing simply models such One-Hot vectors.
</p>

https://github.com/user-attachments/assets/b6f24963-b1a7-4f0b-b5b9-e4a5f6da1040

# Natural Language Processing

<p align="justify">
Natural Language Processing techniques aim to provide a useful number representation to text, naturally these expressions need to manage correctly all different meanings a word have regarding of their context called semantic which is not even static, since natural language and communication changes within human development.
</p>

<p align="justify">
The following techniques provide a summary of strategies made through time to fix and find better data correlations allowing modern day transformers.
</p>

>[!NOTE]
> You will see more refined techniques enhancing their results by reutilizing previous ones with additional adjustments.
</p>

## $${\color{orange}Bag \space of \space Words \space (Bow)}$$

<p align="justify">
Giving a set of texts or documents defined as corpus. Bag of words returns a <b>one vector representation named One-Hot</b> by tracking only the appearance (binary) or the frequency of words on determine group of sentences, although simple it provides a quick brief guide to distinguish and perform feature extraction.
</p>

<p align="justify">
The problems of using bag of words are the lack of word order since it will provide the same One-Hot vector for both binary and frequency based methods since sentences such "I almost told him the truth" and "I told him almost the truth" change dramatically besides giving the same output. Other issues are limited semantics and being insensitive to grammar.
</p>

<p align="justify">
The frequency-based bag of words therefore can be upgraded performing the next seen correlation "Term Frequency-Inverse Document Frequency".
</p>

https://github.com/user-attachments/assets/520d717b-66a7-4d32-a907-37b8f78af605

## $${\color{orange}Term \space Frequency \space - \space Inverse \space Document \space Frequency \space (TF-IDF)}$$

<p align="justify">
Term Frequency-Inverse Document Frequency employs the frequency on each document to <b>extract the number of appearances of each word</b> giving the next expression.
</p>

$$
tf(t,d) = \frac{f(t,d)}{\sum_{t' \in d} f(t', d)}
$$

$$
tf(t,d) = \frac{\text{term occurrence}}{\text{total words}}
$$

<p align="justify">
Once completed, it compares and extracts the Inverse Document Frequency by relative <b>comparing each word giving all the documents</b> computing a logarithm expression escalating toward one the more the same word appears in more documents and therefore returning the value of zero. This method enhances words that are not likely to appear on other documents of the given corpus.
</p>

$$
idf(t, D) = \log \left( \frac{|D|}{|\{ d \in D : t \in d \}|} \right)
$$

$$
idf(t, D) = \log \left( \frac{\text{Number Total Documents}}{\text{Number Documents With the Term}} \right)
$$

<p align="justify">
Finally, the Term Frequency and the Inverse Document Frequency results are multiplied retrieving a combination of both table properties resulting in </b>bigger weights on words that more appear on each document that does not show in others</b>, therefore extracting the most significant words than better describe the given text, performing document clustering at the drawback of being sensitive to corpus where similar contents give less significant results.
</p>

$$
TFIDF(t, d, D) = TF(t, d) \cdot IDF(t, D)
$$

https://github.com/user-attachments/assets/0459047e-40ec-4a38-a40f-8007c08650d4