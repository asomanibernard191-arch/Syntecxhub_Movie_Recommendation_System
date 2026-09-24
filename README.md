# Syntecxhub_Movie-_Recommendation_System
# Task 4: Content-Based Movie Recommendation System

## Overview
This project implements a Content-Based Movie Recommendation System built using the TMDB 5000 Movie Dataset. By combining metadata attributes such as plot overviews, genres, keywords, top cast members, and directors, the system computes feature similarities to recommend relevant movies based on user queries.

---

## Dataset & Feature Engineering
- **Dataset**: TMDB 5000 Movies & Credits
- **Extracted Attributes**:
  - `overview`: Short plot summaries
  - `genres`: Film genre tags
  - `keywords`: Key thematic descriptors
  - `cast`: Top 3 lead actors
  - `crew`: Film director
- **Text Preprocessing**: Merged textual features into a consolidated `tags_string` feature vector, lowercase normalized, and cleaned for vectorization.

---

## Methodology & Model Architecture
1. **Vectorization**: `TfidfVectorizer` (scikit-learn) with English stop-words removed and maximum features capped at 5,000.
2. **Similarity Metric**: Cosine Similarity computed via `linear_kernel` matrix operations.
3. **Engine Logic**: Pairwise similarity scoring to retrieve top $N$ most relevant titles excluding the input query film.

---

## Sample Execution & Results

### Case 1: The Dark Knight
| Rank | Recommended Movie | Cosine Similarity |
| :--- | :--- | :--- |
| 1 | The Dark Knight Rises | 0.4560 |
| 2 | Batman Returns | 0.3830 |
| 3 | Batman Begins | 0.3664 |
| 4 | Batman Forever | 0.3032 |
| 5 | Batman: The Dark Knight Returns, Part 2 | 0.2917 |

### Case 2: Avatar
| Rank | Recommended Movie | Cosine Similarity |
| :--- | :--- | :--- |
| 1 | Falcon Rising | 0.2088 |
| 2 | Battle: Los Angeles | 0.1989 |
| 3 | Apollo 18 | 0.1884 |
| 4 | Star Trek Into Darkness | 0.1754 |
| 5 | Titan A.E. | 0.1693 |

---

## How to Run
1. Clone this repository.
2. Upload `archive.zip` (TMDB dataset) to your Python runtime environment.
3. Open and run `Syntecxhub_Movie_Recommendation_System.ipynb` in Google Colab or Jupyter Notebook.
