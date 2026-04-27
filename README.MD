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
- References

# The Beginning

<p align="justify">
The start of natural language processing relates during cold war where translation of Russian military documents, papers and literacy was essential to the United States to keep up to date. On <b>January 7th, 1954</b>, at IBM the university of Georgetown built the experiment of <b>"Georgetown-IBM"</b> making use of prepared selected phrases to enhance results, nevertheless outside those sentences the model struggle of to capture context then leading to an investment cease in research [1].
</p>

<p align="justify">
Eliza was the <b>first natural language processing program released in 1966 by Joseph Weizenbaum</b> employing basic query consults in a database and adding basic language rules, result into the initial favorable outcomes tricking people on the time to think they were talking with a human being instead of a machine, thriving the Turing test [2].
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
The complexity of natural language processing relies on <b>giving a reliable numeric representation called embedding</b>, to easily overcome this issue preprocessing techniques are applied after segmenting text into individual words named "tokens". A successful tokenization process should be able to adjust and clean the data, disjoin punctuation marks and break off grammar [3].
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
Finally, the Term Frequency and the Inverse Document Frequency results are multiplied retrieving a combination of both table properties resulting in <b>bigger weights on words that more appear on each document that does not show in others</b>, therefore extracting the most significant words than better describe the given text, performing document clustering at the drawback of being sensitive to corpus where similar contents give less significant results.
</p>

$$
TFIDF(t, d, D) = TF(t, d) \cdot IDF(t, D)
$$

https://github.com/user-attachments/assets/0459047e-40ec-4a38-a40f-8007c08650d4

## $${\color{orange}Language \space Models}$$

<p align="justify">
Language models gives a <b>probability of appearance given sequence of words</b>, the simpler techniques employs N-Grams variations, computing the probabilistic distribution following words by the total frequency of large corpus, this primary premise allows to predict texts and even being applied to as a grammar correction, since well written words shows more often given a good dataset of training [4, 5].
</p>

### $${\color{lightskyblue}N-Grams}$$

<p align="justify">
N-Grams were large employed on earlier stages of natural language processing due their obtaining results compare of their complexity, more sophisticated methods were consequently created to face their limitations, natural language tend to be creative a certain word expression is not likely to be captured by simpler, therefore n-grams variations explored later on adequate extra values into the calculations to perform slightly probability toward unseen n-grams in training dataset and small probability to execute a backoff process and decompose the word into more enhance context [4,5 6].
</p>

$$
P(w_1, w_2, \ldots, w_n) \approx P(w_1) \cdot P(w_2 \mid w_1) \cdot P(w_3 \mid w_2) \cdots P(w_n \mid w_{n-1})
$$

$$
P(w_i \mid w_{i-1}) = \frac{\text{count}(w_{i-1}, w_i)}{\text{count}(w_{i-1})}
$$

$$
P(w_i \mid w_{i-1}) = \frac{\text{times "}w_{i-1}, w_i\text{" appears}}{\text{times "}w_{i-1}\text{" appears}}
$$

>[!NOTE]
> Complex language models eventually lead to larger ones, conceiving the name of Large Language Model (LLM) by substituting N-Grams by huge correlated neural networks.

https://github.com/user-attachments/assets/64be7fbc-01c5-4022-b5b5-71a20b784bb5

## $${\color{orange}Word2Vec}$$   

<p align="justify">
One-Hot vectors struggle to encapsulate complex relations of natural language, the main threads to solve are word sparsity due to the given larger corpus and the different values a word can have regarding their context. The incorporation of <b>neural networks, projection layers and language models allows to group words with the same meaning into clusters providing enough abstraction to represent words into vectors</b> and consequently been able to perform basic algebra operations to gather more accurate words prediction [7].
</p>

### $${\color{lightskyblue}Neural \space Networks}$$

<p align="justify">
Artificial Neural Networks are an <b>abstract representation from human brain neuron cells</b>, the cell body integrated by dendrites sends electrical signals, therefore the axon carries the signal into the following neurons, leading to the perception idea [8]. As a result, <b>Artificial Neural Networks are a set of interconnected perceptrons in sets of layers, each connection is called weight and multiples the received value to forward the value into the next perceptrons</b>.
</p>

<p align="justify">
Artificial Neural Networks compute in each epoch a <b>forward propagation</b> in which the network from the input until the output layer spread the received information to following layers up to the last layer, therefore computes the error employing a fitness function comparing the expected value with the obtain value, consequently adjusting each perceptrons connection weight value normally making use of "Stochastic Gradient Descend (SGD)" computing the partial derivate gaining the slope that describes the mathematical function representation that solves the challenge, passing the adjustment into backward direction, archiving <b>backward propagation</b>.
</p>

<p align="justify">
Artificial Neural Networks <b>between layers applies a non-linear transformation given by a activation layer to enable the network to solve non-linear problems</b> due the missing linear representation, meaning it can not be solve through a straight line followed by the linear equation $f(x) = mx + b$ where $mx$ is the slope and $b$ a linear value that adjust the intersection.
</p>

<p align="justify">
Artificial Neural Networks architecture is an entire field of study, accordingly different methods to interconnect each layer and perceptron had been develop, <b>Recurrent Neural Network (RNN) proceed to connect itself a perceptron or beneath layers</b> to solve vanishing or exploding gradient and stabilize training epochs, other future approaches seen into the Transformer architecture is residual training. Additional approaches such <b>Long Short Term Memory Neural Network (LSTM) incorporate an input, forget and output gate</b> to overcome in greater way than Recurrent Neural Networks the problem of vanishing gradient by letting the memory cell update itself to retain or discard information to learn long term dependencies [9].
</p>

https://github.com/user-attachments/assets/81108779-607d-4010-b80e-5f0db9d67d33

### $${\color{lightskyblue}Continuous \space Bag \space of \space Words \space(CBOW)}$$

### $${\color{lightskyblue}Skip-Gram}$$

# References

<p align="justify">
[1] M. Á. Álvarez Carmona, “Aplicaciones básicas de IA en procesamiento de lenguaje natural,” en Macroentrenamiento en Inteligencia Artificial (MeIA) 2025, Semana 1, SECIHTI–CIMAT Monterrey, México, jun. 2025.
</p>

<p align="justify">
[2] D. Bergmann, “The ELIZA effect at work: Avoiding emotional attachment to AI coworkers,” IBM, IBM Think, [Online]. Available: https://www.ibm.com/es-es/think/insights/eliza-effect-avoiding-emotional-attachment-to-ai
</p>

<p align="justify">
[3] J. Murel and E. Kavlakoglu, “What are stemming and lemmatization?,” IBM, [Online]. Available: https://www.ibm.com/think/topics/stemming-lemmatization
</p>

<p align="justify">
[4] S. F. Chen and J. Goodman, “An empirical study of smoothing techniques for language modeling,” Computer Speech & Language, vol. 13, no. 4, pp. 359–394, Oct. 1999.
</p>

<p align="justify">
[5] R. Kneser and H. Ney, “Improved backing-off for m-gram language modeling,” in Proc. IEEE Int. Conf. Acoustics, Speech, and Signal Processing (ICASSP), Detroit, MI, USA, 1995, pp. 181–184.
</p>

<p align="justify">
[6] D. Jurafsky and J. H. Martin, “Kneser-Ney smoothing,” en Speech and Language Processing: An Introduction to Natural Language Processing, Computational Linguistics, and Speech Recognition with Language Models, 3rd ed., online manuscript, Jan. 6, 2026.
</p>

<p align="justify">
[7] T. Mikolov, K. Chen, G. Corrado, and J. Dean, "Efficient Estimation of Word Representations in Vector Space," arXiv preprint arXiv:1301.3781, 2013. doi: 10.48550/arXiv.1301.3781
</p>

<p align="justify">
[8] J. M. Keller, D. Liu, and D. B. Fogel, “Neural networks,” in Fundamentals of Computational Intelligence: Neural Networks, Fuzzy Systems,and Evolutionary Computation. 2016, pp. 5–55
</p>

<p align="justify">
[9] M. Sundermeyer, R. Schlüter, and H. Ney, "LSTM Neural Networks for Language Modeling," in Proc. Interspeech 2012, Portland, OR, USA, Sep. 2012, pp. 194–197. doi: 10.21437/Interspeech.2012-65
</p>