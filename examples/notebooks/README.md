# pyhdb_rs Jupyter Notebooks

Interactive examples demonstrating high-performance SAP HANA analytics with Polars.

## Notebooks

| Notebook | Description |
|----------|-------------|
| [01_quickstart.ipynb](./01_quickstart.ipynb) | Basic connection, queries, and DataFrame integration |
| [02_polars_analytics.ipynb](./02_polars_analytics.ipynb) | Advanced Polars: LazyFrames, window functions, joins |
| [03_streaming_large_data.ipynb](./03_streaming_large_data.ipynb) | Memory-efficient processing of large datasets |
| [04_performance_comparison.ipynb](./04_performance_comparison.ipynb) | Benchmarks vs hdbcli |

## Prerequisites

```bash
uv pip install pyhdb_rs polars pyarrow jupyter
```

## Configuration

Set the HANA connection URL:

```bash
export HANA_TEST_URI="hdbsql://user:password@host:39017"
```

## Quick Start

```bash
cd examples/notebooks
jupyter notebook
```

## Key Concepts

### Zero-Copy Arrow Transfer

```python
from pyhdb_rs import connect

with connect(HANA_URL) as conn:
    with conn.cursor() as cursor:
        # Data flows: HANA → Rust → Arrow → Polars (no copies!)
        df = cursor.execute_polars("SELECT * FROM table")
```

### Streaming Large Data

```python
# Process 100M rows with constant memory
reader = cursor.execute_arrow_batches(query, batch_size=65536)
for batch in reader:
    process(batch)  # Only one batch in memory at a time
```

### Performance Tips

1. **Push filters to HANA** - reduce data transfer
2. **Use `execute_polars()`** - zero-copy DataFrame
3. **Use streaming** for datasets > 1M rows
4. **Prefer Polars LazyFrame** for complex transformations
