# pyhdb-rs

[![PyPI](https://img.shields.io/pypi/v/pyhdb_rs)](https://pypi.org/project/pyhdb_rs)
[![Python](https://img.shields.io/pypi/pyversions/pyhdb_rs)](https://pypi.org/project/pyhdb_rs)
[![License](https://img.shields.io/pypi/l/pyhdb_rs)](https://github.com/bug-ops/pyhdb-rs/blob/main/LICENSE-MIT)

High-performance Python driver for SAP HANA with native Apache Arrow support.

## Features

- **DB-API 2.0 compliant** - Drop-in replacement for existing HANA drivers
- **Zero-copy Arrow integration** - Direct data transfer to Polars and pandas
- **Async support** - Native async/await with connection pooling
- **Type-safe** - Full type hints and strict typing

## Installation

```bash
pip install pyhdb_rs
```

## Quick start

```python
from pyhdb_rs import connect

# Synchronous usage
with connect("hdbsql://user:pass@host:39017") as conn:
    cursor = conn.cursor()
    cursor.execute("SELECT * FROM MY_TABLE")
    for row in cursor:
        print(row)
```

### Polars integration

```python
import pyhdb_rs.polars as hdb

df = hdb.read_hana(
    "SELECT * FROM sales WHERE year = 2024",
    "hdbsql://user:pass@host:39017"
)
print(df.head())
```

### pandas integration

```python
import pyhdb_rs.pandas as hdb

df = hdb.read_hana(
    "SELECT * FROM sales",
    "hdbsql://user:pass@host:39017"
)
```

### Async support

```python
from pyhdb_rs.aio import connect

async with connect("hdbsql://user:pass@host:39017") as conn:
    cursor = await conn.cursor()
    await cursor.execute("SELECT * FROM MY_TABLE")
    async for row in cursor:
        print(row)
```

## Documentation

See the [main repository](https://github.com/bug-ops/pyhdb-rs) for full documentation.

## License

Licensed under either of Apache License, Version 2.0 or MIT license at your option.
