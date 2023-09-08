# Word Embedding with Gensim

Word embedding is a popular technique in natural language processing (NLP) that transforms words or phrases into dense vectors of real numbers. These dense representations capture semantic relationships between words, making them useful for various NLP tasks such as text classification, sentiment analysis, and machine translation.

This repository provides a simple guide and code examples on how to use Gensim, a popular Python library, for creating word embeddings from text data.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Word embeddings are essential for many NLP tasks because they can capture the meaning and context of words in a way that traditional one-hot encoding or bag-of-words representations cannot. Gensim is a powerful library that makes it easy to train word embeddings using various algorithms like Word2Vec, FastText, and more.

## Installation

Before you can start using Gensim for word embedding, you need to install it. You can do this via pip:

```bash
pip install gensim
```

## Usage

1. **Import Gensim and Prepare Text Data**: First, import Gensim and prepare your text data. Your data should be preprocessed and tokenized. Gensim expects a list of sentences, where each sentence is a list of words.

2. **Training the Word Embeddings**:

    ```python
    from gensim.models import Word2Vec

    # Example data (replace with your own)
    sentences = [
        ['this', 'is', 'an', 'example', 'sentence'],
        ['another', 'example', 'sentence'],
        # Add more sentences here
    ]

    # Train Word2Vec model
    model = Word2Vec(sentences, vector_size=100, window=5, min_count=1, sg=0)

    # Save the model
    model.save("word2vec.model")
    ```

    Replace the `sentences` variable with your own data.

3. **Using the Word Embeddings**:

    Once you have trained your word embeddings, you can use them for various NLP tasks, such as finding similar words, word analogies, or as input features for machine learning models.

    ```python
    # Load the saved model
    model = Word2Vec.load("word2vec.model")

    # Find similar words
    similar_words = model.wv.most_similar("example")

    # Perform word analogy
    analogy = model.wv.most_similar(positive=['king', 'woman'], negative=['man'])
    ```

## Examples

Check out the [examples](examples) directory for more detailed code examples and Jupyter notebooks demonstrating how to use Gensim for word embedding.

## Contributing

If you'd like to contribute to this project, please open an issue or submit a pull request. We welcome any contributions that improve documentation, add more examples, or enhance the functionality of this repository.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
