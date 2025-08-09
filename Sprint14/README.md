🎬 Film Junky Union - Movie Review Sentiment Classifier
📌 Project Overview
Film Junky Union, a growing community for classic movie lovers, is building an automated system to detect negative reviews. This repository presents a machine learning pipeline for sentiment analysis on IMDb movie reviews, using polarity-labeled text data to classify reviews as positive or negative.

🎯 Goal: Build a sentiment classifier with an F1 score ≥ 0.85 on the test set.

🧠 Problem Statement
Users of the platform should be able to explore reviews that match their preferences. This requires filtering out negative content, and classifying reviews automatically.

We'll be using IMDb-labeled reviews to:

Clean and preprocess text data

Vectorize using NLP techniques (TF-IDF)

Train multiple machine learning models

Compare performance using F1 score as the primary metric

Deploy the best-performing model for real-world usage

🗂️ Dataset Overview
Each entry includes:

review: textual content of a user’s review (string)

pos: target label (1 = positive, 0 = negative)

Additional columns were present (e.g. genres, runtime_minutes, end_year) but were not used in the modeling due to their irrelevance to the review text.

🧹 Data Preprocessing
Removed unused columns to reduce noise

Normalized review text (lowercasing, punctuation removal)

Tokenized and vectorized using TF-IDF and spaCy

Created train/test splits to evaluate model generalizability

⚙️ Model Training and Evaluation
Models Trained:
Model ID	Methodology	Train F1	Test F1
0	DummyClassifier (Baseline)	0.50	0.50
1	NLTK + TF-IDF + Logistic Regression	0.94	0.88
3	spaCy + TF-IDF + Logistic Regression	0.93	0.88
4	spaCy + TF-IDF + LGBMClassifier	0.91	0.86
9	BERT (300 review sample)	1.00	0.80

✅ All models significantly outperformed the baseline.

⚠️ Note on BERT: Due to hardware limitations, only a sample of 300 reviews was used. Performance is expected to improve with a larger dataset.

🏆 Best Performing Model
Model: NLTK + TF-IDF + Logistic Regression

Test F1 Score: 0.88

Status: ✅ Passes threshold for deployment

🧪 Custom Review Testing
Custom reviews were tested on all models

Some inconsistencies observed in predictions, suggesting room for improvement

Incorporating additional metadata (genres, user scores) may enhance future versions

🔍 Future Enhancements
Expand BERT model to full dataset

Incorporate metadata features (genres, ratings, runtime, etc.)

Explore ensemble models or attention-based networks

Build a user-facing API for real-time review classification

🛠️ Tech Stack
Python (pandas, numpy, sklearn)

NLP: spaCy, NLTK

ML Models: Logistic Regression, LGBMClassifier, DummyClassifier

Deep Learning: BERT (HuggingFace Transformers)

📁 Repository Structure
bash
Copy
Edit
film-junky-sentiment/
│
├── data/                   # Raw and cleaned datasets
├── notebooks/              # EDA and model training notebooks
├── models/                 # Serialized model files
├── scripts/                # Text preprocessing and training scripts
├── README.md               # Project documentation
└── requirements.txt        # Python dependencies
✅ Conclusion
This project successfully demonstrates a robust pipeline for text-based sentiment classification with:

Accurate model performance (F1 > 0.85)

Scalable text preprocessing

Multiple modeling approaches

🎬 With this system, Film Junky Union can confidently filter and classify movie reviews, enhancing user experience for classic film lovers.


