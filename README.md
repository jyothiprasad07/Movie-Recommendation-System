# 🎬 Movie Recommendation System

This project is a **Movie Recommendation System** built using Python and powered by **content-based filtering**. It suggests movies similar to a user-selected movie by analyzing key features like genres, cast, crew, and keywords from a dataset of over 4,800 movies.

---

## ✅ Features

- Preprocesses and cleans movie data from the TMDB dataset.
- Extracts important features such as genres, cast, crew, and keywords.
- Combines features into a unified **"tags"** column for similarity calculations.
- Utilizes **Natural Language Processing (NLP)** for stemming and cleaning data.
- Computes movie similarity using **cosine similarity**.
- Provides **top 5 movie recommendations** based on user input.
- Interactive **web interface using Streamlit**.

---

## 📊 Dataset

- **Movies Dataset**: `tmdb_5000_movies.csv`  
- **Credits Dataset**: `tmdb_5000_credits.csv`

---

## ⚙️ How It Works

### 1. 🧹 Data Preprocessing
- Merges `movies` and `credits` datasets on the `title` column.
- Cleans and extracts relevant columns:
  - `movie_id`, `title`, `overview`, `genres`, `keywords`, `cast`, `crew`.
- Handles missing values and removes duplicates.

### 2. 🔍 Feature Engineering
- Converts JSON-like strings in `genres`, `keywords`, `cast`, and `crew` into lists of keywords.
- Limits the cast list to the top 3 actors and extracts the **director** from the crew.
- Combines `overview`, `genres`, `keywords`, `cast`, and `crew` into a single **"tags"** column.

### 3. 🧠 Text Preprocessing
- Converts tags to lowercase.
- Applies **stemming** to reduce words to their base forms using the **Porter Stemmer**.

### 4. 📐 Vectorization
- Converts the tags into numerical vectors using **CountVectorizer**:
  - Maximum of 5,000 features.
  - Removes stopwords.

### 5. 📏 Similarity Calculation
- Calculates the **cosine similarity** between movie vectors.

### 6. 🎯 Recommendation
- Fetches the **top 5 most similar movies** to the user-selected movie based on cosine similarity scores.

---

## 🛠️ Installation and Setup

### 🔹 1. Clone the Repository

```bash
git clone https://github.com/anandreddy05/Movie-Recommendation-System.git
cd Movie-Recommendation-System
