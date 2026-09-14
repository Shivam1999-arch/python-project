**🎬 Fandango Movie Ratings — Bias Analysis**

📌 Overview

This capstone project investigates whether Fandango (an online movie ticketing platform) displays inflated star ratings for movies compared to other rating platforms — potentially to encourage more ticket sales.

The analysis is based on the FiveThirtyEight article: "Be Suspicious Of Online Movie Ratings, Especially Fandango's", and uses the original dataset published on 538's GitHub.

❓ Question

Does Fandango's displayed star rating match the actual average rating of a movie, or is there a bias toward showing higher scores than the movie truly deserves — when compared with Rotten Tomatoes, Metacritic, and IMDb?

**🛠️ Tools & Technologies Used**

Python
Pandas (data wrangling)
Matplotlib & Seaborn (data visualization)
Jupyter Notebook

**📂 Dataset Description**

1. fandango_scrape.csv — every film pulled from Fandango

Column	Description
FILM	Movie name
STARS	Star rating displayed on Fandango.com
RATING	Actual average rating pulled from the HTML
VOTES	Number of reviews at the time of pulling

2. all_sites_scores.csv — aggregated ratings across platforms

Column	Description
FILM	Movie name
RottenTomatoes	Rotten Tomatoes critic (Tomatometer) score
RottenTomatoes_User	Rotten Tomatoes user score
Metacritic	Metacritic critic score
Metacritic_User	Metacritic user score
IMDB	IMDb user score
Metacritic_user_vote_count	Number of Metacritic user votes
IMDB_user_vote_count	Number of IMDb user votes

Data pulled from Fandango on August 24, 2015.

🔍 Analysis Workflow

Explored Fandango's displayed STARS vs actual RATING for potential rounding-up bias
Filtered dataset to only films with 30+ fan reviews for reliability
Compared Fandango ratings against normalized scores from Rotten Tomatoes, Metacritic, and IMDb
Visualized rating distributions and differences using KDE plots, bar charts, and clustermaps
Identified specific movies with the largest rating discrepancies (e.g., Taken 3)

📊 Key Findings

Fandango's displayed star ratings are consistently higher than the actual computed ratings, especially for lower-quality films
Compared to Rotten Tomatoes, Metacritic, and IMDb, Fandango ratings show a clear positive bias
Taken 3 (2015) was the biggest outlier — Fandango displayed 4.5 stars, while its average score across other platforms was only 1.86
The findings align with the original 538 article's conclusion: Fandango ratings appear inflated, likely because the platform also profits from ticket sales

**📁 Repository Structure**

├── README.md
├── 00-Capstone-Project.ipynb     # Full analysis notebook
├── data/
│   ├── fandango_scrape.csv
│   └── all_sites_scores.csv

**🚀 How to Use**

Clone this repository
Install dependencies: pip install pandas matplotlib seaborn jupyter
Place fandango_scrape.csv and all_sites_scores.csv in a data/ folder
Open and run 00-Capstone-Project.ipynb in Jupyter Notebook
