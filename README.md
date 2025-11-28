# N-gram Analysis of Text Data

## Project Description

This project demonstrates text analysis using N-grams (unigrams, bigrams, trigrams) with an example text describing the nature of Kyrgyzstan. It includes text preprocessing, N-gram extraction, and visualization of results.

## Features

- 📝 Text preprocessing (cleaning, tokenization, lemmatization)
- 🔍 Extraction of unigrams, bigrams, and trigrams
- 📊 Visualization of top-10 most frequent N-grams
- 🎨 Stylish plots with dark theme design

## Requirements

```bash
pip install pandas numpy nltk matplotlib
```

## Installation

1. Clone the repository or copy the code
2. Install required libraries:

```python
import pandas as pd
import numpy as np
import re
import nltk
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize
from nltk.stem import WordNetLemmatizer
from collections import Counter
import matplotlib.pyplot as plt
```

3. Download NLTK resources:

```python
nltk.download('punkt')
nltk.download('punkt_tab')
nltk.download('stopwords')
nltk.download('wordnet')
```

## Usage

### 1. Load Text

Prepare your text for analysis and split it into sentences:

```python
text = """
Your text here...
"""

sentences = text.split(".")
df = pd.DataFrame(sentences, columns=["text"])
df = df[df["text"].str.strip() != ""]
```

### 2. Text Preprocessing

The `clean_text()` function performs:
- ✔ Lowercasing
- ✔ Removing punctuation
- ✔ Removing numbers
- ✔ Tokenization
- ✔ Stopword removal
- ✔ Lemmatization

```python
lemmatizer = WordNetLemmatizer()
stop_words = set(stopwords.words("english"))

def clean_text(text):
    text = text.lower()
    text = re.sub(r'[^\w\s]', '', text)
    text = re.sub(r'\d+', '', text)
    
    tokens = word_tokenize(text)
    tokens = [w for w in tokens if w not in stop_words]
    tokens = [lemmatizer.lemmatize(w) for w in tokens]
    
    return tokens

df["clean_tokens"] = df["text"].apply(clean_text)
```

### 3. Generate N-grams

```python
def get_ngrams(tokens_list, n):
    ngrams = []
    for tokens in tokens_list:
        for i in range(len(tokens)-n+1):
            ngrams.append(tuple(tokens[i:i+n]))
    return ngrams

unigrams = get_ngrams(df["clean_tokens"], 1)
bigrams  = get_ngrams(df["clean_tokens"], 2)
trigrams = get_ngrams(df["clean_tokens"], 3)
```

### 4. Analyze Results

Display the top-10 most frequent N-grams:

```python
print("Top Unigrams:", Counter(unigrams).most_common(10))
print("Top Bigrams:", Counter(bigrams).most_common(10))
print("Top Trigrams:", Counter(trigrams).most_common(10))
```

### 5. Visualization

Create plots to visualize the results:

```python
plt.style.use("dark_background")

# Unigrams
uni_counts = Counter(unigrams).most_common(10)
labels = [' '.join(u[0]) for u in uni_counts]
values = [u[1] for u in uni_counts]

plt.figure(figsize=(12, 6))
colors = cm.cool(np.linspace(0.3, 1, len(values)))

plt.barh(labels, values, color=colors, edgecolor='#ffffff', linewidth=1.2)
plt.xlabel("Frequency", fontsize=13, color="white")
plt.title("Top 10 Unigrams", fontsize=18, weight="bold", color="white")
plt.grid(axis='x', linestyle='--', alpha=0.3)

plt.gca().invert_yaxis()
plt.show()
```

## Project Structure

```
├── ngram_analysis.py       # Main script
├── README.md              # This file
└── requirements.txt       # Dependencies
```

## Example Results

After running the script, you will get:

1. **Top Unigrams** - most frequent individual words
2. **Top Bigrams** - most frequent word pairs
3. **Top Trigrams** - most frequent word triplets
4. **Three plots** visualizing N-gram frequencies

## Customization

You can customize:

- **Number of N-grams**: change the parameter in `most_common(10)`
- **Color scheme**: use different palettes (`cm.cool`, `cm.viridis`, `cm.plasma`)
- **Plot size**: modify `figsize=(12, 6)`
- **Stopwords language**: replace `"english"` with another language

## Sample Text

The project uses text about the nature of Kyrgyzstan, including descriptions of:
- Mountain landscapes
- Issyk-Kul Lake
- Alpine meadows and pastures
- Ecosystem diversity
- Wildlife and nature reserves

## Author

Created for demonstration of text analysis using N-gram methods.

## License

Free to use for educational purposes.

---

**Note**: Make sure all NLTK resources are downloaded before running the script.
