# Information Retrieval System

A collection of foundational NLP and text-processing notebooks covering core concepts in information retrieval — from pattern matching and compression to classification and clustering.

> **Repo:** [github.com/karthik-ryali/information-retrieval-system](https://github.com/karthik-ryali/information-retrieval-system)

---

## Notebooks

| Notebook | Topic | Key Concepts |
|----------|-------|-------------|
| [`text_pattern.ipynb`](#text-pattern-matching) | Substring search | Sliding window, brute-force O(n×m) |
| [`compressed_text.ipynb`](#text-compression) | Run-Length Encoding | Lossless compression, encode/decode |
| [`n_gram.ipynb`](#n-gram-spell-correction) | Spell correction | Character n-grams, Jaccard similarity |
| [`tfidf.ipynb`](#tf-idf) | Term weighting | TF, IDF, keyword extraction |
| [`classification.ipynb`](#text-classification) | Spam detection | CountVectorizer, Logistic Regression |
| [`clustering.ipynb`](#text-clustering) | Topic grouping | TF-IDF + K-Means, unsupervised learning |

---

## Text Pattern Matching

[`text_pattern.ipynb`](./text_pattern.ipynb)

Implements substring search from scratch using a sliding window approach — no built-in `.find()`.

- Scans every position in the main string and compares character-by-character
- Handles overlapping matches and reports all occurrences
- Time complexity: O(n × m)

---

## Text Compression

[`compressed_text.ipynb`](./compressed_text.ipynb)

Implements **Run-Length Encoding (RLE)** — a lossless compression technique that collapses consecutive repeated characters.

- `rle_compress`: encodes runs into `char + count` pairs
- `rle_decompress`: reconstructs the original string perfectly
- Includes compression ratio analysis across different input types

---

## N-Gram Spell Correction

[`n_gram.ipynb`](./n_gram.ipynb)

Suggests corrections for misspelled words using character-level n-gram similarity.

- Generates bigrams/trigrams with boundary markers (`#word#`)
- Scores candidates using **Jaccard similarity**: `|A ∩ B| / |A ∪ B|`
- Returns the dictionary word with the highest overlap score

---

## TF-IDF

[`tfidf.ipynb`](./tfidf.ipynb)

Builds TF-IDF from scratch using `numpy` and `pandas` — no sklearn shortcuts.

- **TF**: word frequency relative to document length
- **IDF**: `log10(total_docs / docs_containing_word)` — penalises common words
- **TF-IDF**: product of both; high score = frequent here, rare elsewhere
- Extracts top keywords per document from the final matrix

---

## Text Classification

[`classification.ipynb`](./classification.ipynb)

Trains a spam detector using a bag-of-words pipeline.

- `CountVectorizer` converts messages into word-count feature vectors
- `LogisticRegression` learns weights per word
- Outputs predicted label + spam probability for new messages

---

## Text Clustering

[`clustering.ipynb`](./clustering.ipynb)

Groups sentences by topic without any labels — fully unsupervised.

- TF-IDF vectors represent each sentence numerically
- **K-Means** assigns sentences to the nearest centroid iteratively
- Centroid inspection reveals which words define each cluster

---

## Stack

- Python 3
- `numpy`, `pandas`
- `scikit-learn`

---

## Run Locally

```bash
git clone https://github.com/karthik-ryali/information-retrieval-system.git
cd information-retrieval-system
jupyter notebook
```

Or open any notebook directly in [Google Colab](https://colab.research.google.com/).