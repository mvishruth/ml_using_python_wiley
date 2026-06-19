# Pandas set_option() Reference Guide

## Display Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `display.max_rows` | int | 60 | Maximum rows to display when printing a DataFrame |
| `display.max_columns` | int | 20 | Maximum columns to display when printing a DataFrame |
| `display.max_colwidth` | int/None | 50 | Maximum width of columns - truncate if wider |
| `display.width` | int | 80 | Width of display in characters |
| `display.float_format` | callable | None | Format function for floating point numbers |
| `display.precision` | int | 6 | Decimal places for floating point numbers |
| `display.max_info_columns` | int | 100 | Max columns to display in DataFrame.info() |
| `display.memory_usage` | bool | True | Display memory usage in DataFrame.info() |
| `display.large_repr` | str | 'truncate' | How to display large DataFrames ('truncate' or 'info') |
| `display.max_info_rows` | int/None | 1690785 | Rows threshold for DataFrame.info() to switch output |
| `display.show_dimensions` | bool | True | Show dimensions of DataFrame/Series |
| `display.chop_threshold` | float | None | Round to zero any numeric value less than threshold |
| `display.colspace` | int | None | Space between columns in DataFrame display |
| `display.max_rows` | int | 60 | Max rows to print |
| `display.min_rows` | int | 10 | Rows to print if DataFrame exceeds max_rows |

## I/O Options

| Option | Description |
|--------|-------------|
| `io.excel.xlsx.writer` | Default Excel writer |
| `io.parquet.engine` | Default Parquet engine |
| `io.sql.engine` | Default SQL engine |

## Mode Options

| Option | Description |
|--------|-------------|
| `mode.copy_on_write` | Enable copy-on-write mode |
| `mode.data_manager` | Data manager type ('block' or 'array') |

## Computation Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `compute.use_bottleneck` | bool | True | Use bottleneck for numeric operations |
| `compute.use_numba` | bool | False | Use numba for numeric operations |

## Usage Examples

```python
# Set maximum rows displayed
pd.set_option('display.max_rows', 100)

# Set maximum columns displayed (you're already using this!)
pd.set_option('display.max_columns', 7)

# Set floating point format
pd.set_option('display.float_format', lambda x: '%.3f' % x)

# Set column width
pd.set_option('display.max_colwidth', 100)

# Set display precision
pd.set_option('display.precision', 2)

# Set display width
pd.set_option('display.width', 120)

# Show/hide dimensions
pd.set_option('display.show_dimensions', True)

# Reset to default
pd.reset_option('display.max_columns')

# Reset all options
pd.reset_option('all')

# View current settings
pd.get_option('display.max_columns')