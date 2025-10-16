Here’s how you can update your **README.md** to include the instructions for importing the database, running the data cleaning scripts, and integrating the new steps seamlessly:

---

# NYC Taxi Trips Dashboard (Urban Mobility Data Explorer)
A web dashboard for exploring taxi trip data with interactive filtering, charts, and maps.

---

## Team Members
- Samuel NIYONKURU  `backend & documentation`
- David NGARAMBE  `backend`
- Attorney Valois NIYIGABA  `frontend`
- Prudence Browns  `frontend & documentation`

---

## Project Structure
```
nyc-taxi-dashboard/
├── backend/
│   ├── app.py                # Flask backend
│   ├── requirements.txt      # Backend dependencies
│   └── ...
├── frontend/
│   ├── index.html            # Frontend HTML
│   ├── app.js                # Frontend JavaScript
│   └── ...
├── data/
│   ├── raw/                  # Place `train.csv` here
│   ├── processed/            # Place `cleaned_trips.csv` here
│   ├── links/                # Google Drive links for datasets
│   ├── schema.sql            # Database schema
│   └── data_dump.sql         # Database data dump
├── scripts/
│   ├── clean_cleaning.py     # Initial data cleaning script
│   └── update_cleaned_data.py # Collects column issues for DB insertion
└── README.md                 # This file
```

---

## Setup Instructions

### 1) Download the Dataset
Download the dataset files and place them in the following locations:
- **Train dataset**: [`train.csv`](https://drive.google.com/file/d/1hIwlem1l4fNdSJCi1MiM9QJv3SSWZGJe/view?usp=drive_link) → `./data/raw/train.csv`
- **Cleaned dataset**: [`cleaned_trips.csv`](https://drive.google.com/file/d/17t7OYgXkZPPhE6-x1uHWkh8bqRphL6O1/view?usp=sharing) → `./data/processed/cleaned_trips.csv`

---

### 2) Clean and Prepare the Data
Before importing the data into MySQL, you must clean and validate it:
1. Run the initial cleaning script:
   ```bash
   python scripts/clean_cleaning.py
   ```
   This script processes the raw data and generates a cleaned version in `./data/processed/cleaned_trips.csv`.

2. Run the column validation script:
   ```bash
   python scripts/update_cleaned_data.py
   ```
   This script checks for column issues that may arise during database insertion and logs them for review.

---

### 3) Import the Database
After cleaning the data, import the schema and data into MySQL:

1. **Create the database**:
   ```bash
   mysql -u your_username -p -e "CREATE DATABASE nyc_taxi;"
   ```

2. **Import the schema**:
   ```bash
   mysql -u your_username -p nyc_taxi < data/schema.sql
   ```

3. **Import the data**:
   ```bash
   mysql -u your_username -p nyc_taxi < data/data_dump.sql
   ```

---

### 4) Install Python and Packages
Follow the [Python and package installation instructions](#2-install-python-and-packages) as described in the previous README.

---

### 5) Install and Configure MySQL
Follow the [MySQL installation and configuration instructions](#3-install-and-configure-mysql) as described in the previous README.

---

### 6) Configure Environment Variables
Create a `.env` file inside `backend/` with your database connection details:
```
DB_HOST=localhost
DB_USER=nyc_user
DB_PASSWORD=your_password
DB_NAME=nyc_taxi
DB_PORT=3306
```

---

### 7) Run the Backend and Frontend
Follow the [backend](#5-run-the-backend) and [frontend](#6-run-the-frontend) instructions as described in the previous README.

---

## Troubleshooting
- **Data cleaning issues**: Ensure all scripts in `scripts/` are executable and dependencies are installed.
- **MySQL import errors**: Verify that the database and user exist, and that the schema and data files are correctly formatted.
- **Connection errors**: Double-check your `.env` file and MySQL user permissions.

---

## License
This project is licensed under the MIT License.
