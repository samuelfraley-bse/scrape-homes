# Geocode Workflow

This folder is the shortest path for turning `data/idealista_barcelona_sale_urls.csv` into geocoded output.

## What You Need

- `../data/idealista_barcelona_sale_urls.csv` as the input file
- Python dependencies installed with `uv`
- Jupyter so you can run the notebook

## Quick Start

From the repo root:

```powershell
uv sync
uv run python -m ipykernel install --user --name scrape-idealista --display-name "Python (scrape-idealista)"
uv run jupyter lab
```

Then open `geocode/geocode_addresses.ipynb` and run the cells from top to bottom.

## What The Notebook Does

1. Loads `../data/idealista_barcelona_sale_urls.csv`
2. Pulls the best available address-like text from each listing
3. Keeps rows with a usable street number for exact geocoding
4. Geocodes unique addresses with OpenStreetMap Nominatim
5. Reuses `../data/idealista_geocode_cache.csv` so reruns are faster
6. Writes row-level output and a summary back into `../data/`

## Expected Output

After a successful run, you should see:

- `../data/idealista_barcelona_sale_urls_geocoded.csv`
- `../data/idealista_barcelona_sale_urls_geocode_summary.csv`
- `../data/idealista_geocode_cache.csv`

## Notes

- The input CSV is not currently checked in here, so if it is missing, add it to `data/` with the exact filename `idealista_barcelona_sale_urls.csv`.
- A standalone retry script is not currently present in this repo, so the notebook is the main supported geocoding path.
