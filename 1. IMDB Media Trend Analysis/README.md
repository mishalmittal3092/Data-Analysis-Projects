[![Kaggle Notebook](https://img.shields.io/badge/Kaggle-Notebook-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/code/mishalmittal/imdb-movies-data-analysis)

## Overview
An exploratory data analysis of the IMDB Movies Dataset (~2.59M titles, 1920–2022),
examining production volume trends, audience engagement patterns, genre evolution and
content certification shifts across 102 years
of global media output.

---

## Data Cleaning

| Column | Issue | Treatment |
|--------|-------|-----------|
| `year` | Raw string e.g. `(2018 TV Series–2022)` — year and type combined | Vectorised regex extraction via `str.extractall()` |
| `genre` | Comma-separated multi-label e.g. `"Drama,Crime"` | Exploded per title for all genre-level analysis |
| `votes` | Comma Seperated float values in string type| replaced the commas and typecasted into integer sequentially |
| `certificate` | Mixed case, inconsistent naming across regions | Normalised and mapped to three categories: Kids / Family / Adult |
| `directors_id` / `stars_id` | Comma-separated IMDB nm-IDs per title | Exploded and mapped via JSON lookup. `Anonymous` exchanged|
| Movie vs. Series | Mentioned as substring in year column for some of the records | Keyword extraction from raw `year` string with year-range fallback |

---

## Analytical Questions

1. How has global media production volume changed from 1920 to 2022?
2. Does audience engagement (votes) track production volume, or do the two diverge?
3. Which genres have grown or declined across each decade?
4. Which genres attract the most engagement — and does volume drive engagement?
5. How has the Kids / Family / Adult content balance shifted over time?
---

## Conclusions & Business Insights

### What the data tells us

- **Production volume peaked in 2019 and collapsed during COVID:**  
  Global titles released grew from ~10,000/year in 1980 to a peak of **114,229 in 2019**,  
  then fell over 60% to ~30,000 by 2022.

- **Movies account for ~83% of all titles but the Series gap is closing fast:**  
  In 1990 series represented roughly 35% of total output. By 2019 that share had risen to  
  over 42%, and series vote engagement quadrupled in the same window.

- **Drama is the universal genre glue:**  
  Drama appears in **516,398 titles** — more than any other genre.

- **Fan engagement is an internet-era phenomenon, not a content-era one:**  
  Total votes across all titles were negligible before 1995. The inflection point is  
  **1999–2002**, directly coinciding with IMDB's mainstream adoption post-Amazon acquisition  
  (1998). 

- **Adult-rated content engagement was virtually zero before 1995 — then exploded with the internet:**  
  The inflection in Adult content begins sharply at **1995–2010**,  
  directly tracking mainstream internet adoption.

  

---
