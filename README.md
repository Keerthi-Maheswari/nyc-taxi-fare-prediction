# Predicting NYC Yellow Taxi Fares

Group 4, PhDAI 733 M21 (Python Application for Data Analytics in AI), University of Cumberlands
Team: Harsha Sanka, Keerthi Maheswari Mallampaty, Sri Navya Pajjuru

## Project
Predict the fare of a NYC yellow taxi trip from distance, trip time, pick-up hour and weekend, using the official TLC trip records for September 2026 (3.88 million trips, 100,000 sampled). Deliverable: Data Preprocessing and Initial Model Development.

## Results (20,000 held-out test trips)
| Model | Average error (MAE) | R² |
|---|---|---|
| Guess the average fare | $12.93 | 0.000 |
| Linear regression, distance only | $5.28 | 0.787 |
| Linear regression, all four inputs | $3.52 | 0.839 |
| Random forest | $3.45 | 0.838 |
| Random forest (tuned) | $3.18 | 0.855 |

Errors are larger for trips over 10 miles ($7.47) and night trips ($4.51).

## Repository layout
- `notebooks/` analysis notebook (runs in Google Colab)
- `docs/` report (APA) and presentation
- `figures/` charts used in the report
- `data/` instructions for downloading the data (data file is not committed)
- `requirements.txt` Python packages

## Run it
In Colab: open the notebook from this repository (Colab > File > Open notebook > GitHub tab), then Runtime > Run all.
The notebook reads the data from Google Drive (`file_path` in step 2). Change `file_path` to wherever you saved the parquet file. To run locally, also remove the two Google Drive lines and run `pip install -r requirements.txt`.

Tools: pandas, NumPy, Matplotlib, Seaborn, scikit-learn, Google Colab, GitHub. Dask was not needed for a 100,000-trip sample.

## Team workflow
1. Never commit directly to `main`.
2. Create a branch for your task: `git checkout -b yourname/short-task`.
3. Commit small changes with clear messages, push, and open a pull request.
4. A teammate reviews and approves before merging.
5. Pull the latest `main` before starting new work: `git pull origin main`.
6. The random seed is fixed (42) so everyone gets the same numbers.

| Member | Focus |
|---|---|
| [Name] | Problem framing and report |
| [Name] | Exploration and visualization |
| [Name] | Data preparation |
| [Name] | Modeling and evaluation |

## Data source
New York City Taxi and Limousine Commission. (2026). TLC trip record data: Yellow taxi trip records, September 2026 [Data set]. https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page
