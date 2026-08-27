# 🎬 Movie Recommender System

A **content-based movie recommendation system** built with Python and Streamlit that recommends movies similar to a user's selected movie.

The application uses movie metadata to calculate similarity between movies and provides the **top 5 recommendations**, along with their posters fetched from the TMDB API.

## 🚀 Features

* 🎥 Select a movie from an interactive dropdown
* 🤖 Generate movie recommendations based on similarity
* ⭐ Display the top 5 recommended movies
* 🖼️ Fetch and display movie posters using the TMDB API
* ⚡ Precomputed similarity data for faster recommendations
* 🌐 Simple interactive web interface using Streamlit

## 🛠️ Tech Stack

* **Python**
* **Streamlit** — Web application interface
* **Pandas** — Data processing
* **NumPy** — Numerical operations
* **Requests** — TMDB API requests
* **Pickle** — Storing and loading processed movie data and similarity matrix
* **TMDB API** — Movie poster and metadata retrieval

## 🧠 How It Works

The recommendation system follows a simple content-based recommendation approach.

```text
TMDB Movie Dataset
       │
       ▼
Data Cleaning & Preprocessing
       │
       ▼
Movie Feature Extraction
       │
       ▼
Similarity Calculation
       │
       ▼
Saved Movie Data + Similarity Matrix
       │
       ▼
Streamlit Application
       │
       ▼
User Selects Movie
       │
       ▼
Find Similar Movies
       │
       ▼
Top 5 Recommendations
       │
       ▼
Fetch Movie Posters from TMDB
```

## 📊 Dataset

The model was developed using the **TMDB 5000 Movie Metadata** dataset.

The dataset contains information such as:

* Movie title
* Genres
* Keywords
* Overview
* Cast
* Crew
* Popularity
* Release date
* Ratings
* Vote count
* Movie ID

The training notebook contains approximately **4,803 movies** from the movie metadata dataset.

## 🔍 Recommendation Process

The application loads two preprocessed files:

```text
model/
├── movie_list.pkl
└── similarity.pkl
```

`movie_list.pkl` contains the processed movie information, while `similarity.pkl` contains the precomputed similarity values used to find movies related to the selected title.

When a user selects a movie:

1. The application finds the selected movie in the dataset.
2. It retrieves the corresponding similarity scores.
3. Movies are sorted according to their similarity.
4. The top 5 similar movies are selected.
5. Movie IDs are sent to the TMDB API.
6. Posters are retrieved and displayed in the Streamlit interface.

## 🖥️ Application

The application provides a simple interface where users can select a movie and click **"Show Recommendation"** to receive five recommendations.

## 📁 Project Structure

```text
Movie-Recommender-System/
│
├── app.py
├── notebook86c26b4f17.ipynb
├── README.md
│
└── model/
    ├── movie_list.pkl
    └── similarity.pkl
```

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/subratshakya/Movie-Recommender-System.git
cd Movie-Recommender-System
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

On Linux/macOS:

```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install streamlit pandas numpy requests
```

## ▶️ Run the Application

Start the Streamlit application:

```bash
streamlit run app.py
```

The application will open in your browser at the local Streamlit address.

## 🔑 TMDB API

The application uses the **TMDB API** to retrieve movie posters based on movie IDs. The poster URL is constructed using the movie ID returned by the TMDB API.

For production use, API credentials should be stored securely using environment variables or Streamlit secrets rather than directly inside the source code.

## 📌 Project Highlights

* Built an interactive **content-based movie recommendation application**.
* Processed the **TMDB 5000 Movie Metadata dataset** for recommendation purposes.
* Used precomputed similarity scores to efficiently retrieve similar movies.
* Integrated the **TMDB API** to dynamically fetch movie posters.
* Developed a simple and user-friendly interface using **Streamlit**.

## 🔮 Future Improvements

* Add movie ratings and reviews.
* Add genre-based filtering.
* Display movie descriptions, ratings, cast, and release dates.
* Improve recommendation quality using additional movie features.
* Secure the TMDB API key using environment variables.
* Deploy the application for public access.

## 👨‍💻 Author

**Subrat Shakya**

GitHub:
https://github.com/subratshakya

---

⭐ If you find this project useful, consider giving the repository a star!
