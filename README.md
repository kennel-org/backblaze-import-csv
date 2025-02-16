# backblaze-import-csv

This shell script is designed to insert CSV data from pre-processed Backblaze files into a MariaDB table. The script should be placed directly in the `/var/tmp` directory, and it expects the CSV file to be stored in the `/var/tmp/mariadb` directory.

## Features

- **CSV File Handling:** The script reads a CSV file containing pre-processed Backblaze data from `/var/tmp/mariadb`.
- **Database Insertion:** It uses the configured database connection details (host, username, password, and database name) to insert data into a specified MariaDB table.
- **Permission Modification:** After processing, the script creates an output log or backup file and changes its permissions using the `chmod` command to enhance security. Adjust the permission settings as necessary for your environment.

## Prerequisites

- A Unix-like operating system (Linux, macOS, etc.) with Bash.
- MariaDB installed and accessible, along with the required client tools (e.g., `mysql` or `mariadb` client).
- Correct database connection details (host, user, password, database name) configured within the script.

## Directory Structure

    /var/tmp/
    ├── insert_csv.sh    # The shell script
    └── mariadb/
        └── data.csv     # CSV file containing pre-processed Backblaze data

## Setup

1. **Place the CSV File:**  
   Ensure your pre-processed Backblaze CSV file is placed in the `/var/tmp/mariadb` directory.  
   Example: `/var/tmp/mariadb/data.csv`

2. **Configure the Script:**  
   - Verify that the CSV file path within the script points to `/var/tmp/mariadb/data.csv`.
   - Update the database connection information (host, username, password, database name) in the script.
   - Review the file permission modification settings (`chmod` command) in the script and adjust them as necessary.

3. **Set Execution Permissions:**  
   Grant execution rights to the shell script: `chmod +x /var/tmp/insert_csv.sh`

## Usage

1. Change to the `/var/tmp` directory: `cd /var/tmp`  
2. Execute the script: `./insert_csv.sh`

The script will:
- Read the CSV file from `/var/tmp/mariadb`.
- Insert the CSV data into the specified MariaDB table.
- Create an output file (e.g., a log or backup file) and modify its permissions as configured.
