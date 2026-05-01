# scrape-idealista

This repo is organized so a new classmate can focus on one task: geocoding `data/idealista_barcelona_sale_urls.csv`.

## Start Here

If you want to geocode listing addresses, go straight to `geocode/README.md`.

The main notebook is:

```text
geocode/geocode_addresses.ipynb
```

It reads:

```text
data/idealista_barcelona_sale_urls.csv
```

and writes geocoded output back into `data/`.

## Setup

From the repo root:

```powershell
uv sync
uv run python -m ipykernel install --user --name scrape-idealista --display-name "Python (scrape-idealista)"
uv run jupyter lab
```

## Repo Layout

```text
data/       input files, cached data, and geocoded outputs
geocode/    the classmate-friendly geocoding workflow
scrape/     older scraping notebooks and text fixtures
analysis/   analysis notebooks
scripts/    utility scripts if/when they are added back
```

## What Is Where

- `geocode/` contains the notebook you should run for address geocoding.
- `scrape/` keeps the scraping materials for background context, but they are not required for the geocoding workflow.
- `analysis/` contains notebooks used after data collection/geocoding.
- `data/` contains outputs already generated in this repo plus the expected location for the input CSV.

## Current Scope

Some notebooks and loose scripts from older work are no longer present in the repo. This reorganization keeps and documents the files that are currently checked in or sitting in the working tree.
