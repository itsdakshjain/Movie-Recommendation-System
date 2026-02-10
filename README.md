#  Movie Recommendation System
**A Full-Stack AI Web Application**

This project is a movie recommendation engine that suggests films based on content similarity. It features a decoupled architecture with a FastAPI backend and a Streamlit frontend, both deployed in the cloud.

##  Live Links
* **Frontend (UI):**&nbsp;[![Streamlit](https://img.shields.io/badge/Streamlit-%23FF4B4B.svg?style=flat&logo=streamlit&logoColor=white)](https://itsdakshjain-movie-recommendation-system.streamlit.app/)
* **Backend (API):** &nbsp; [![Render](https://img.shields.io/badge/Render-%23430098.svg?style=flat&logo=render&logoColor=white)](https://movie-recommendation-system-gci4.onrender.com/docs)


##  Architecture
The system follows a **Microservices Architecture**:
1. **Backend (FastAPI):** Handles the machine learning logic, similarity scores, and TMDB API integration. Hosted on **Render**.
2. **Frontend (Streamlit):** Provides a responsive UI for users to search movies and view recommendations. Hosted on **Streamlit Community Cloud**.

##  Machine Learning Pipeline
The recommendation engine follows a sophisticated NLP workflow to understand movie context:

1. **Data Engineering**: 
   - Cleaned a dataset of 45,000+ movies.
   - Handled complex data structures using `ast.literal_eval` to extract genres from stringified dictionaries.
2. **Text Preprocessing (NLP)**: 
   - **Tokenization & Regex**: Removed noise and punctuations.
   - **Stopword Removal**: Filtered non-informative English words.
   - **Lemmatization**: Used `WordNetLemmatizer` to reduce words to their root form (e.g., "running" to "run").
3. **Vectorization**:
   - Implemented **TF-IDF (Term Frequency-Inverse Document Frequency)** with an `ngram_range` of (1,2). This captures both individual words and meaningful pairs of words.
4. **Similarity Engine**:
   - Utilized **Cosine Similarity** to calculate the distance between movie vectors in a 50,000-dimensional space.

---

##  Project Structure
```
  ├── data/           # Raw Data
  ├── models/         # Serialized .pkl files (TF-IDF matrix, indices, model)
  ├── notebooks/      # recommendation.ipynb (Research & EDA)
  ├── src/
  │   ├── app.py      # Streamlit UI Source Code
  │   └── main.py     # FastAPI Backend Source Code
  ├── requirements.txt # Library dependencies
  └── runtime.txt      # Python version specification (3.11.9)
```
---

##  Tech Stack
* **Language:** Python 3.11.9
* **Machine Learning:** Scikit-learn (TF-IDF Vectorizer & Cosine Similarity), Pandas, NumPy, NLTK, Joblib
* **Web Frameworks:** FastAPI (Backend), Streamlit (Frontend)
* **APIs:** TMDB (The Movie Database) for posters and metadata
* **Deployment:** Render (Backend), Streamlit Cloud (Frontend)

---

## ⚙️ Setup & Installation
**Step 1: Clone the Repository**

```bash
git clone https://github.com/itsdakshjain/Movie-Recommendation-System
cd Movie-Recommendation-System
```

**Step 2: Create a Virtual Environment**

```bash
python -m venv venv
# On Windows:
venv\Scripts\activate
# On Mac/Linux:
source venv/bin/activate
```

**Step 3: Install Dependencies**

```bash
pip install -r requirements.txt
```

**Step 4: Run the Application**

```bash
#Run Backend
uvicorn src.main:app --reload
#Run Frontend
streamlit run src/app.py
```

---

## License
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
> This project is licensed under the **MIT License**—a permissive license that allows for personal and commercial use while providing a disclaimer of warranty. See the [LICENSE](LICENSE) file for the full text.

## Contact & Credits
**Developer:** Daksh Jain  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/daksh-jain-6b31772b9/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/itsdakshjain)
