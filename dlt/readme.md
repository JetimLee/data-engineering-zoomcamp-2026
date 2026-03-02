# NYC Taxi Pipeline - dlt Workshop Homework

## Quick Start

### Step 1: Install dependencies

```bash
pip install "dlt[duckdb]"
```

### Step 2: Run the pipeline

```bash
python taxi_pipeline.py
```

This will:

- Fetch all pages from the NYC taxi API (1,000 records per page)
- Load them into a local DuckDB database
- Print the total row count when done

### Step 3: Explore the data

```bash
python query_taxi_data.py
```

This runs common queries against the loaded data (row counts, averages, distributions, etc.).

### Step 4: Use dlt dashboard (optional)

```bash
dlt pipeline taxi_pipeline show
```

## Files

| File                 | Purpose                                        |
| -------------------- | ---------------------------------------------- |
| `taxi_pipeline.py`   | Main pipeline - fetches data from API → DuckDB |
| `query_taxi_data.py` | Query script to explore loaded data            |

## API Details

| Property   | Value                                                                                   |
| ---------- | --------------------------------------------------------------------------------------- |
| Base URL   | `https://us-central1-dlthub-analytics.cloudfunctions.net/data_engineering_zoomcamp_api` |
| Format     | Paginated JSON                                                                          |
| Page Size  | 1,000 records per page                                                                  |
| Pagination | Page number param, stop on empty page                                                   |
