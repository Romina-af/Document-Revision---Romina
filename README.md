# LogLens

LogLens is a local command-line Python tool that counts records in CSV log files. It allows users to count all records or filter them by a specific log level. This tool is intended for undergraduate computing students and new technical interns who have basic knowledge of CSV files and terminal commands.

## Requirements

- Python 3.10 or newer
- Basic knowledge of terminal commands
- A CSV file with the required column headers

LogLens uses only the Python standard library. No additional packages or dependencies need to be installed.

## Getting Started

Follow the [Installation and Setup Guide](docs/INSTALL.md) to download the project files, locate the repository root, and run LogLens for the first time.

All commands should be run from the repository root, where `loglens.py` is located. Depending on your computer, you may need to use `python3` or `py` instead of `python`.

## Input File Format

The input must be a CSV file containing the following column headers:

| Column | Description |
| --- | --- |
| `timestamp` | The time of the log entry |
| `level` | The log level |
| `message` | The message associated with the log entry |

The accepted log levels are `INFO`, `WARN`, and `ERROR`. These values must be uppercase.

A [sample CSV file](data/sample_logs.csv) is included in the repository for testing.

## Using LogLens

### Count all records

To count all records in the sample CSV file, run:

```bash
python loglens.py --file data/sample_logs.csv
```

Expected output:

```text
Records matching ALL: 6
```

### Count records by log level

To count only records with the `ERROR` level, run:

```bash
python loglens.py --file data/sample_logs.csv --level ERROR
```

Expected output:

```text
Records matching ERROR: 2
```

### Command-line arguments

| Argument | Description | Required |
| --- | --- | --- |
| `--file` | Specifies the path to the input CSV file. | Yes |
| `--level` | Filters records by `INFO`, `WARN`, or `ERROR`. | No |

To view the available command-line options, run:

```bash
python loglens.py --help
```

## Limitations and Data Privacy

- LogLens counts log records but does not diagnose system failures.
- It reads the input CSV file without repairing, rewriting, or modifying it.
- All processing takes place locally. LogLens does not upload, transmit, or store input data outside the user's computer.

## Getting Help

If you encounter a problem, refer to the [Troubleshooting section](docs/INSTALL.md#troubleshooting) of the installation guide.

When reporting an issue on GitHub, clearly describe the problem and provide a sanitized, minimal example if needed. Do not publicly share private or sensitive log data.
