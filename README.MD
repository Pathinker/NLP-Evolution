# Natural Language Processing

<p align="justify">
Natural Language Processing (NLP) refers to the methodologies and complexity employed on computers to understand human language called "natural language" such ambiguity, polysemous words or irony. Trought its development, different techniques have led to the current Large Language Moldes (LLMs). The initial favorable outcomes employed language rules and One-Hot vectors, therefore integrating different approaches within Neural Network connections.
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
  - $${\color{orange}Transformers}$$   
      - $${\color{lightskyblue}Seq2Seq \space (Encoder \space - \space Decoder)}$$
- Video

# The Beginning

<p align="justify">
The start of natural language processing relates during cold war where translation of Russian military documents, papers and literacy was essential to the United States to keep up to date. On January 7th, 1954, at IBM the university of Georgetown built the experiment of "Georgetown-IBM" making use of prepared selected phrases to enhance results, nevertheless outside those sentences the model struggle of to capture context then leading to an investment cease in research.
</p>

<p align="justify">
Eliza was the first natural language processing program released in 1966 by Joseph Weizenbaum employing basic query consults in a database and adding basic language rules, result into the initial favorable outcomes tricking people on the time to think they were talking with a human being instead of a machine, thriving the Turing test.
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
The complexity of natural language processing relies on giving a reliable numeric representation called embedding, to easily overcome this issue preprocessing techniques are applied after segmenting text into individual words named "tokens". A successful tokenization process should be able to adjust and clean the data, disjoin punctuation marks and break off grammar.
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