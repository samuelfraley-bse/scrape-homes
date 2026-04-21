# scrape-idealista

Notebooks for collecting Idealista Barcelona housing listings for research.

## Setup

```powershell
uv sync
uv run python -m ipykernel install --user --name scrape-idealista --display-name "Python (scrape-idealista)"
uv run jupyter lab
```

Use `scrape_idealista_barcelona_sales_details.ipynb` for the full workflow. It paginates result pages, collects listing URLs, visits each listing page, and writes:

```text
data/idealista_barcelona_sale_properties_details.csv
```

If `data/idealista_barcelona_sale_urls.csv` already exists and you only want to process listing detail pages in gentle resumable batches, use:

```text
scrape_idealista_barcelona_detail_batches.ipynb
```
