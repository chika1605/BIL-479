📘 README — HW1: Text Cleaning & N-Gram Analysis
Natural Language Processing Course — Homework 1 (Metin Temizleme & N-Gram Analizi)

Student: Chyngyz Almambetov
Submission File: hw1.ipynb
Deadline: November 28, 2025
Score Weight: Accuracy (60%) + Reporting (40%)

📌 1. Overview

This homework focuses on fundamental Natural Language Processing (NLP) preprocessing steps, including:

Text cleaning

Tokenization

Stopword removal

Lemmatization

N-gram generation (Unigram, Bigram, Trigram)

Frequency analysis

Visualization of most common n-grams

All steps are implemented inside the Jupyter notebook hw1.ipynb using Python and NLTK.

📚 2. Dataset

For this assignment, a custom English dataset was created describing the natural landscapes of Kyrgyzstan.
The text includes mountains, lakes, forests, wildlife, nomadic culture, and ecosystems — providing rich vocabulary for n-gram analysis.

🧹 3. Text Preprocessing Steps

The following preprocessing operations were applied:

✔ Lowercasing

Convert all text to lowercase to ensure consistency.

✔ Removing Punctuation

All non-alphabetical characters were removed using regex.

✔ Removing Digits

Numbers were removed to focus purely on lexical patterns.

✔ Tokenization

The text was split into individual words using NLTK’s word_tokenize.

✔ Stopword Removal

English stopwords (e.g., the, is, and, from) were removed to emphasize meaningful content.

✔ Lemmatization

Words were reduced to their base form using WordNetLemmatizer.
Example: mountains → mountain, lakes → lake

This ensures better grouping during n-gram frequency analysis.

🔠 4. N-Gram Analysis

N-grams represent sequences of words:

Unigram: 1-word sequence

Bigram: 2-word sequence

Trigram: 3-word sequence

Functions were written to automatically extract all possible n-grams from the cleaned tokens.

📊 5. Frequency Analysis

The top 10 most common n-grams were computed using Python's Counter:

Top Unigrams: shows dominant keywords

Top Bigrams: reveals common word associations

Top Trigrams: captures longer semantic structures

Example significant n-grams:

Unigrams: kyrgyzstan, mountain, lake, nature, ecosystem

Bigrams: snow capped, natural landscape, mountain ranges

Trigrams: one largest deepest, mountain pasture known

(Exact values depend on the final text.)

🎨 6. Visualizations

To clearly present frequency results, the notebook includes:

✔ Horizontal bar charts (Top 10)

For:

Unigrams

Bigrams

Trigrams

✔ Custom styling

Dark mode theme

Gradient color palettes

Clear labels

Grid lines for readability

This ensures professional and visually appealing output.

🧪 7. Technologies Used

Python 3

NLTK

Pandas

Matplotlib

NumPy

Jupyter / Google Colab

🧾 8. File Structure
HW1/
│── hw1.ipynb          # Main notebook with implementation
│── README.md          # Documentation (this file)
└── assets/            # (Optional) screenshots or exported plots

✅ 9. Conclusion

This homework demonstrates the essential NLP preprocessing pipeline.
By applying lemmatization, tokenization, stopword removal, and n-gram extraction, the text becomes structured and ready for computational linguistic analysis.

The visualizations and frequency statistics provide insights into the lexical patterns of the dataset, making this assignment a strong foundation for more advanced NLP tasks such as sentiment analysis, topic modeling, or transformer-based analysis.

🙋‍♂️ 10. Author

Chyngyz Almambetov
Software Engineering Student
Kyrgyz-Turkish Manas University
