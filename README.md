# Extract
Downloaded csv files from 3 different personnel bank accounts, including two credit card accounts and a checking account.

| File 1 Columns    | File 2 Columns  | File 3 Columns    |
| -------------     | -------------   | -------------     |
| Transaction Date  | Date            | Posted Date       |
| Post Date         | Description     | Reference Number  |
| Description       | Amount          | Payee             |
| Type              | Running Bal.    | Address           |
| Amount            |                 | Amount            |

# Transform
Following transformations are done to consolidate data from three files.
- Converted date columns from string to dates
- Removed credit card payment rows/records
- Added transaction type (credit vs debit), depending on the amount being negative vs positive
- Converted all transaction descriptions to lower case for easy category classification
- Classified transactions into personalized categories depending on transaction description
- Converted debit amounts to positives, so data is positive in all rows, as we have transaction type column added

# Load
Data is loaded/appened into PostgreSQL database table using SQLAlchemy. 

# Query data
Now that data is loaded into PostgreSQL, it can be queried using SQLAlchemy or directly in PostgreSQL.
