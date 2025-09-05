# Movie Recommender System

A content-based movie recommendation system built with Python and Streamlit that suggests movies based on similarity analysis using the TMDb 5000 Movie Dataset.

## Features

- Interactive web interface using Streamlit
- Content-based filtering using movie metadata
- Movie poster fetching from The Movie Database (TMDb) API
- Cosine similarity for recommendation logic
- Displays top 5 similar movies with posters

## Demo

The application provides a dropdown menu to select a movie, and upon clicking "Show Recommendation", it displays 5 similar movies with their posters in a clean, responsive layout.

## Dataset

This project uses the TMDb 5000 Movie Dataset which includes:
- `tmdb_5000_movies.csv` - Movie metadata (genres, keywords, overview, etc.)
- `tmdb_5000_credits.csv` - Cast and crew information
- Dataset link "https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata"

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/movie-recommender-system.git
cd movie-recommender-system
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

3. Create a `requirements.txt` file with the following dependencies:
```
streamlit
pandas
numpy
requests
scikit-learn
pickle
```

## Setup

1. Download the TMDb 5000 Movie Dataset and place the CSV files in the project directory
2. Run the Jupyter notebook `Movie-Recommender.ipynb` to:
   - Process and clean the data
   - Create the similarity matrix
   - Generate the required pickle files (`movie_list.pkl` and `similarity.pkl`)

## Usage

1. Start the Streamlit application:
```bash
streamlit run app.py
```

2. Open your web browser and navigate to `http://localhost:8501`

3. Select a movie from the dropdown menu

4. Click "Show Recommendation" to get 5 similar movie suggestions

## File Structure

```
movie-recommender-system/
│
├── app.py                     # Main Streamlit application
├── Movie-Recommender.ipynb    # Data processing and model training
├── tmdb_5000_movies.csv       # Movie dataset
├── tmdb_5000_credits.csv      # Credits dataset
├── movie_list.pkl             # Processed movie data
├── similarity.pkl             # Similarity matrix
├── requirements.txt           # Project dependencies
└── README.md                  # Project documentation
```

## How It Works

1. **Data Processing**: Movie metadata is cleaned and processed, extracting features like genres, keywords, cast, and crew
2. **Feature Engineering**: Text features are combined and vectorized using CountVectorizer
3. **Similarity Calculation**: Cosine similarity is computed between all movies
4. **Recommendation**: For a selected movie, the system finds the most similar movies based on the similarity matrix
5. **Poster Fetching**: Movie posters are dynamically fetched from TMDb API

## API Key

The application uses TMDb API to fetch movie posters. The API key is currently hardcoded in the application. For production use:

1. Get your API key from [The Movie Database](https://www.themoviedb.org/settings/api)
2. Replace the hardcoded API key in `app.py` with your own
3. Consider using environment variables for security

## Technologies Used

- **Python**: Core programming language
- **Streamlit**: Web application framework
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing
- **Scikit-learn**: Machine learning library for vectorization and similarity
- **Requests**: HTTP library for API calls
- **Pickle**: Data serialization

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Future Enhancements

- Add user rating-based collaborative filtering
- Implement hybrid recommendation approach
- Add movie details and trailers
- Include user authentication and personalized recommendations
- Add more sophisticated NLP techniques for better content analysis
- Implement caching for better performance

## Acknowledgments

- The Movie Database (TMDb) for providing the movie dataset and API
- Streamlit for the excellent web application framework
- The open-source community for the various Python libraries used

