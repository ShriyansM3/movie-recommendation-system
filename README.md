# Full-Stack Content-Based Movie Recommendation System

A movie recommendation system that suggests similar movies based on content features using TF-IDF vectorization and cosine similarity. The application exposes a FastAPI backend and retrieves movie metadata and posters using the TMDb API.

## Features

* Recommend movies similar to a given title using content-based filtering
* Compute recommendations using TF-IDF vectorization and cosine similarity
* Fetch movie details and posters from the TMDb API
* Gracefully handle movies with limited metadata using a fallback recommendation strategy
* FastAPI backend for serving recommendations
* Simple web interface for user interaction

## Tech Stack

* Python
* FastAPI
* scikit-learn
* Pandas
* TMDb API
* Streamlit
* httpx

## How It Works
1. Movie metadata is preprocessed and transformed into a 50,000-feature TF-IDF representation across 45K+ movies.
2. A cosine similarity matrix is computed to measure similarity between movies.
3. When a user searches for a movie, the system retrieves the most similar titles based on these vectors.
4. If sufficient metadata is unavailable, the application falls back to genre- and popularity-based recommendations from TMDb.
5. The backend serves recommendation requests through FastAPI, using `httpx.AsyncClient` to fetch movie details and posters from TMDb concurrently, with custom HTTP 502 handling for failed upstream requests.

## Project Structure

```text
Movie-Recommendation-System/
├── app.py
├── main.py
├── models/
├── data/
├── notebooks/
└── requirements.txt
```

## Installation

```bash
git clone <repository-url>
cd Movie-Recommendation-System
pip install -r requirements.txt
```

Run the backend:

```bash
uvicorn main:app --reload
```

Run the frontend:

```bash
streamlit run app.py
```

## Future Improvements

* Hybrid recommendation using collaborative filtering
* Personalized user profiles and watch history
* Advanced semantic search using embeddings
* Caching for external API responses
* Support for TV shows and multilingual recommendations

## License

This project was built for educational and learning purposes.
