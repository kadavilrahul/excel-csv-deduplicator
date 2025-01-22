# Excel and CSV File Deduplicator
This Python tool helps you remove duplicate entries from your Excel and CSV files. It can find duplicates both within a single file and across multiple files, specifically focusing on the second column (column B) of your data.
Tested and developed on Ubuntu 24.04.1 LTS (Noble Numbat).

## Requirements
- Python 3
- Required Python packages:
  - pandas
  - openpyxl

## Installation

Install the required Python packages using one of these methods:

1. Direct installation:
```bash
pip install pandas openpyxl
```

2. Using requirements.txt:
```bash
pip install -r requirements.txt
```

## File Structure
The program expects the following structure:
```
deduplication/
├── main.py
└── data_csv/
    └── your_files.csv
```

Place all your CSV and Excel files that need deduplication in the `data_csv` folder.

## How to Use

1. Place your files in the `data_csv` folder
2. Run the program:
```bash
python3 main.py
```

3. The program will:
   - Automatically use the `data_csv` folder
   - Use column B (second column) for deduplication
   - Show you which file is newest
   - Ask you to confirm if the newest file is correct
   - Create a backup of your files before processing
   - Remove duplicates and show statistics

## Features
- Automatically processes files from the `data_csv` folder
- Uses the second column (column B) for deduplication
- Creates backups before making any changes
- Handles both Excel (.xls, .xlsx) and CSV files
- Removes duplicates both within files and across multiple files
- Provides detailed statistics about the deduplication process

## Output
The program will show:
- List of all files found
- Number of rows in original files
- Number of duplicates removed (both internal and external)
- Percentage reduction in rows
- Location of backup files

## Backup Files
Before processing, the program creates a backup of your newest file with the format:
```
original_filename_backup_YYYYMMDD_HHMMSS.extension
```

## Error Handling
- Creates backups before any modifications
- Validates file existence and column availability
- Provides clear error messages if something goes wrong
- Restores original file if an error occurs during processing
