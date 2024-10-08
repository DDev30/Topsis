# Topsis-Devansh-102218067

**Topsis-Devansh-102218067** is a Python package for performing TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution), a multi-criteria decision-making method. This package is designed to help rank alternatives based on their distance from an ideal solution.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
  - [Command-Line Interface (CLI)](#command-line-interface-cli)
  - [Example](#example)
- [Input File Format](#input-file-format)
- [Output File Format](#output-file-format)
- [Error Handling](#error-handling)
- [License](#license)

## Installation

### Prerequisites

- Python
- `pip` (Python package installer)

### Installation Commands

To install the package locally:

```sh
pip install topsis-Devansh-102218067
```

Once installed, the `topsis` command will be available for use in your command line.

## Usage

### Command-Line Interface (CLI)

You can run the TOPSIS analysis using the `topsis` command. The syntax is as follows:

```sh
Topsis <weights> <impacts> <InputFileName> <OutputFileName>
```

- **inputFileName**: Path to the input CSV file containing the data.
- **weights**: Comma-separated weights for each criterion (e.g., "0.3,0.2,0.5").
- **impacts**: Comma-separated impacts for each criterion, where `'+'` denotes a beneficial criterion and `'-'` denotes a non-beneficial criterion (e.g., "+,+,-").
- **resultFileName**: Path to the output CSV file where the results will be saved.

### Example

Suppose you have a CSV file named `data.csv` with the following structure:

```csv
Ind,C1,C2,C3,C4
A1,250,16,12,5
A2,200,25,8,3
A3,300,20,10,4
A4,275,22,9,4.5
```

You can run the TOPSIS analysis with:

```sh
topsis "0.3,0.2,0.4,0.1" "+,+,-,+," data.csv result.csv
```

This command will generate a `result.csv` file with the TOPSIS scores and ranks.

## Input File Format

- The input file MUST be in CSV format.
- The first column should contain labels for the alternatives (e.g., "A1", "A2").
- The remaining columns should contain numeric data for the criteria.

Example:

```csv
Ind,C1,C2,C3,C4
A1,250,16,12,5
A2,200,25,8,3
A3,300,20,10,4
A4,275,22,9,4.5
```

## Output File Format

The output file will be a CSV file with the original data plus two additional columns:

- **Topsis Score**: The calculated TOPSIS score for each alternative.
- **Rank**: The rank of each alternative based on the TOPSIS score.

Example:

```csv
Ind,C1,C2,C3,C4,Topsis Score,Rank
A1,250,16,12,5,0.68,2
A2,200,25,8,3,0.55,4
A3,300,20,10,4,0.78,1
A4,275,22,9,4.5,0.65,3
```

## Error Handling

The program includes robust error handling for common issues:

- **File Not Found**: An error message will be displayed if the input file is missing.
- **Non-Numeric Data**: The program will check for non-numeric data in criteria columns.
- **Unequal Weights and Impacts**: The number of weights and impacts must match the number of criteria.
- **Incorrect Impacts**: Impacts must be either `'+'` or `'-'`.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
