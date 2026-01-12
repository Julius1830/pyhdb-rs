# pyhdb_rs Jupyter Notebooks

Interactive examples demonstrating high-performance SAP HANA analytics with Polars and zero-copy Arrow integration.

## Notebooks

| Notebook | Description | Key Topics |
|----------|-------------|------------|
| [01_quickstart.ipynb](./01_quickstart.ipynb) | Basic connection and DataFrame integration | DB-API 2.0, `execute_polars()`, parameters |
| [02_polars_analytics.ipynb](./02_polars_analytics.ipynb) | Advanced Polars analytics | LazyFrames, window functions, joins, pivots |
| [03_streaming_large_data.ipynb](./03_streaming_large_data.ipynb) | Memory-efficient large dataset processing | `RecordBatchReader`, parallel processing |
| [04_performance_comparison.ipynb](./04_performance_comparison.ipynb) | Benchmarks vs hdbcli | Throughput, memory usage, concurrency |

## Prerequisites

```bash
uv pip install pyhdb_rs polars pyarrow jupyter
```

For local development, build from source:

```bash
cd /path/to/pyhdb-rs
maturin develop --release
```

## Configuration

Set the HANA connection URL as an environment variable:

```bash
export HANA_TEST_URI="hdbsql://USER:PASSWORD@HOST:39017"
```

> [!IMPORTANT]
> Replace `USER`, `PASSWORD`, and `HOST` with your SAP HANA credentials. Never commit credentials to version control.

## Quick start

```bash
cd examples/notebooks
jupyter notebook
```

Or open `.ipynb` files directly in VS Code with the Jupyter extension.

## Key concepts

### Zero-copy Arrow transfer

Data flows directly from SAP HANA through Rust to Polars without Python object creation:

```python
from pyhdb_rs import connect

with connect(HANA_URL) as conn:
    with conn.cursor() as cursor:
        # HANA → Rust → Arrow → Polars (zero copies)
        df = cursor.execute_polars("SELECT * FROM sales")
```

### Streaming large datasets

Process datasets larger than available memory with constant memory usage:

```python
reader = cursor.execute_arrow_batches(query, batch_size=65536)
for batch in reader:
    process(batch)  # Only one batch in memory at a time
```

> [!TIP]
> Use streaming (`execute_arrow_batches`) for datasets exceeding 1M rows. Tune `batch_size` based on row width.

### Performance recommendations

1. **Push filters to HANA** — reduce network transfer by filtering at the source
2. **Use `execute_polars()`** — zero-copy DataFrame creation
3. **Use `execute_arrow_batches()`** — constant memory for large datasets
4. **Prefer Polars LazyFrame** — optimize complex transformation chains
5. **Partition queries** — enable parallel processing across connections

## Diagrams

Notebooks include interactive Mermaid diagrams for:

- Data pipeline architecture
- Streaming aggregation flow
- Parallel processing topology
- Incremental processing sequences

Diagrams render automatically in Jupyter and on GitHub.

## License

Part of the [pyhdb_rs](https://github.com/bug-ops/pyhdb-rs) project. See [LICENSE](../../LICENSE-APACHE) for details.
