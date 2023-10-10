# CliniTex
A Multilayered Approach to Deep Medical Text Understanding 

Abstract:

In the domain of medical text comprehension, our study presents a comprehensive model that leverages various levels of linguistic information. We start by utilizing a Token-Level Model to process sequences of words or tokens, transforming textual data into numerical representations. Simultaneously, a Character-Level Model delves into fine-grained details within words, capturing character-level nuances. Furthermore, we incorporate a Line Number Model, which uses one-hot-encoded line numbers to provide context for the current line within the document. Similarly, a Total Lines Model is employed to represent the overall document's length.

The core of our approach lies in the Token-Character Hybrid Embedding, which amalgamates both token-level and character-level information, thereby enriching the model's understanding by encompassing both word and character intricacies. This embedding is further enhanced in the Token-Character-Positional Tribrid Embedding step, where contextual information regarding line numbers and total lines is fused, ensuring that each token's context within the document is accurately captured.

To make informed predictions, we have developed a dedicated Output Layer that processes the tribrid embedding, allowing the model to provide label probabilities. Finally, our research culminates in the seamless integration of these components into a unified TensorFlow model. This holistic model takes input in the form of tokens, characters, line numbers, and total lines, skillfully processes them through their respective components, synergistically combines the information, and generates insightful predictions, thus significantly enhancing our ability to understand complex medical text data.

Data Source:
Data used for this research: PubMed RCT Dataset ( https://github.com/Franck-Dernoncourt/pubmed-rct )

Models Overview

Model 0: Getting a Baseline
Our initial model utilizes a TF-IDF Multinomial Naive Bayes classifier, as recommended by Scikit-Learn's machine learning guidelines. This model employs the TF-IDF vectorization technique to convert abstract sentences into numerical representations and then classifies sentences using the Multinomial Naive Bayes algorithm.

Model 2: Feature Extraction with Pretrained Token Embeddings
This model focuses on feature extraction using pretrained token embeddings, enhancing the understanding of the underlying linguistic context.

Model 3: Conv1D with Character Embeddings
Here, we employ a Convolutional Neural Network (Conv1D) with character embeddings to capture fine-grained character-level information.

Model 4: Combining Pretrained Token Embeddings + Character Embeddings (Hybrid Embedding Layer)
In this model, we combine pretrained token embeddings with character embeddings to create a hybrid embedding layer that captures both word and character intricacies.

Model 5: Transfer Learning with Pretrained Token Embeddings + Character Embeddings + Positional Embeddings (Tribrid Embedding)
Model 5 represents a transfer learning approach where pretrained token embeddings, character embeddings, and positional embeddings are combined to provide a richer understanding of medical text.

Model training Results:


<img width="701" alt="Screenshot 2023-10-10 at 9 47 13 PM" src="https://github.com/abby1712/CliniTex/assets/72368959/a70101db-13b1-4c04-9b82-c59c79d5d0d5">

Working: 

<img width="1030" alt="Screenshot 2023-10-10 at 9 47 38 PM" src="https://github.com/abby1712/CliniTex/assets/72368959/ce2ded1f-8acd-4366-8f1b-8c637e041590">

<img width="1021" alt="Screenshot 2023-10-10 at 9 47 52 PM" src="https://github.com/abby1712/CliniTex/assets/72368959/647e1516-3625-4bc3-b1fc-481c94e243cb">


Conclusion:
In conclusion, our research introduces a sophisticated model designed to enhance our understanding of medical text data. By combining token and character-level information with contextual cues such as line numbers and total lines, our model provides a comprehensive approach to text analysis. This enables more accurate predictions and a deeper comprehension of complex medical documents, ultimately contributing to advancements in healthcare and medical research.
