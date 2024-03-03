# Financial Contracts Data Fetcher

This Python script is designed to fetch, process, and log financial contract data from a specified API endpoint. It focuses on collecting data for various contract types, such as trades, quotes, and open interest, and provides functionalities for logging the status of fetched contracts, handling errors, and storing processed data efficiently.

## Features
- Fetch contract data from a local API.
- Process and filter contracts based on root symbols and contract types.
- Log errors and successful fetches in JSON format.
- Store processed contract data in structured directories.
- Support for multiple contract roots and types.
- Dynamic date range processing for contract data collection.

## Requirements
Before you can run this script, you need to have the following installed:
Python 3.x
Libraries: requests, numpy, pandas, tqdm
You can install the necessary libraries using pip:

```
pip install requests numpy pandas tqdm
```

## Configuration
Before running the script, ensure you configure the following variables according to your needs:

- `base_directory`: The base directory where all data will be saved.
- `roots`: List of root symbols for which contracts need to be fetched.
- `contract_types`: Types of contracts to fetch (e.g., trade, quote, open_interest).
- `url`, `url_1`, `url_2`: API endpoints for fetching contract data.
- `Trading_Days`: List of trading day symbols to ensure fetching of relevant contracts only.
- `interval`: Interval for data fetching, adjust as per requirement.
- `days_from_start_to_keep`: Number of days to keep data from the start date.



## Functions 
```python
# Function to fetch contract data based on root symbol, date, and contract type
def fetch_contracts(root, date, contract_type):
    ...

# Function to log error contracts to a JSON file
def log_strike_error_to_json(error_contracts_list, base_directory):
    ...

# Function to log successful contracts to a JSON file
def log_strike_success_to_json(successful_contracts_list, base_directory):
    ...

# Utility function to fetch and format data from an API endpoint
def fetch_and_format_data(endpoint, columns, root, expiration, strike, right, start_date, end_date):
    ...

# Helper function to convert milliseconds to time of day
def ms_to_time(ms):
    ...

# Function to fetch and filter contracts data
def fetch_contracts_filtered_by_root(date, contract_type, url):
    ...

# Main function to collect and process contracts data
def collect_contracts_data(date, contract_types, url, url_1, url_2, roots, base_directory):
    ...

# Utility function to check and drop identical columns in a DataFrame
def check_and_drop_identical_columns(df, potential_duplicates, suffix):
    ...

# Function to process individual contracts and generate required data
def process_contracts(root, expiration, strike, right, start_date, end_date, interval, base_directory):
    ...

# Function to load logged contracts from JSON files
def load_logged_contracts(folder_path, filename):
    ...

# Function to normalize dictionary keys and extract relevant values
def get_normalized_entry(entry, keys):
    ...

# Entry function to begin the data processing and logging
def begin_process(start_date, end_date, roots, date_list, contract_types, url, url_1, url_2, Trading_Days, base_directory, special_roots, _root1, _root2, _root3, _root4, _root4, interval, days_from_start_to_keep):
    ...

# Function to find matching contracts and log them as successful
def find_matching_contracts_and_log_success(roots, base_directory, date_list):
    ...
```

## Note
This script is designed to work with a local API running at `http://127.0.0.1:25510`. Ensure that the API is running and accessible before executing the script. Adjust the `url`, `url_1`, and `url_2` variables as per your API configuration.
