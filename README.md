Here's a more structured and visually appealing version of the README for GitHub, with a cleaner layout and some formatting improvements. I've also added some headers and bullet points to enhance readability.

---

```markdown
# NYC Taxi Trips Dashboard

A web dashboard for exploring NYC taxi trip data with interactive filtering, charts, and maps.

## **Team Members**
- **Samuel NIYONKURU**
- **David NGARAMBE**
- **Attorney Valois NIYIGABA**
- **Prudence Browns**

---

## **Project Structure**
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
│   └── links/                # Google Drive links for datasets
├── scripts/
│   └── data_cleaning.py      # Data cleaning script
└── README.md                 # This file

````

---

## **Setup Instructions**

### **1. Download the Dataset**
The dataset files are hosted on Google Drive due to their large size. Download them and place them in the correct directories:

- **Train Dataset**: [Download `train.csv`](your-google-drive-link-for-train.csv)  
  - **Location**: `./data/raw/train.csv`
  
- **Cleaned Dataset**: [Download `cleaned_trips.csv`](your-google-drive-link-for-cleaned_trips.csv)  
  - **Location**: `./data/processed/cleaned_trips.csv`

---

### **2. Install Dependencies**

#### **Backend and Script Dependencies**
The backend and scripts require Python 3.8+ and the following packages. Install them using `pip`:

```bash
pip install flask flask-cors mysql-connector-python gunicorn pandas
````

Alternatively, you can install all dependencies at once by running:

```bash
cd backend
pip install -r requirements.txt
```

#### **Frontend Dependencies**

The frontend is powered by modern JavaScript libraries loaded via CDN in `index.html`. No installation is required for the frontend. The libraries include:

* **Chart.js**
* **Leaflet.js**
* **Papa Parse**

---

### **3. Set Up the Database**

This project uses MySQL. Follow the instructions below depending on your operating system:

#### **Windows**

1. **Install MySQL**:

   * Download MySQL from [mysql.com](https://dev.mysql.com/downloads/installer/).
   * Follow the installation instructions.

2. **Create a Database**:

   * Open MySQL Command Line Client or MySQL Workbench.
   * Run the following commands:

     ```sql
     CREATE DATABASE nyc_taxi;
     USE nyc_taxi;
     ```
   * Import the database schema or run the `scripts/db_setup.py` script to create the tables and insert data.

#### **macOS**

1. **Install MySQL**:

   * Use Homebrew to install MySQL:

     ```bash
     brew install mysql
     brew services start mysql
     ```

2. **Create a Database**:

   * Open terminal and run:

     ```bash
     mysql -u root -p
     ```
   * Enter your MySQL password and run:

     ```sql
     CREATE DATABASE nyc_taxi;
     USE nyc_taxi;
     ```
   * Import the database schema or run the `scripts/db_setup.py` script.

#### **Ubuntu Linux**

1. **Install MySQL**:

   * Update your package list and install MySQL:

     ```bash
     sudo apt update
     sudo apt install mysql-server
     sudo systemctl start mysql
     ```

2. **Create a Database**:

   * Open terminal and run:

     ```bash
     sudo mysql -u root -p
     ```
   * Enter your MySQL password and run:

     ```sql
     CREATE DATABASE nyc_taxi;
     USE nyc_taxi;
     ```
   * Import the database schema or run the `scripts/db_setup.py` script.

---

### **4. Configure Environment Variables**

Create a `.env` file in the `backend/` directory with your MySQL connection details:

```
DB_HOST=localhost
DB_USER=your-mysql-username
DB_PASSWORD=your-mysql-password
DB_NAME=nyc_taxi
```

---

### **5. Run the Backend**

Navigate to the `backend/` directory and start the Flask server:

```bash
cd backend
python app.py
```

The backend will be available at `http://localhost:5000`.

---

### **6. Run the Frontend**

For best performance, serve the frontend using a local server. You can do this with Python's built-in server:

```bash
cd frontend
python -m http.server 8000
```

Then open `http://localhost:8000` in your browser.

---

### **7. Video Walkthrough**

Watch the video walkthrough to see the dashboard in action:
[Video Walkthrough](your-video-link)

---

## **Troubleshooting**

* **MySQL Connection Issues**: Ensure MySQL is running and the credentials in `.env` are correct.
* **Frontend Not Loading**: Make sure you're serving the frontend using a local server, e.g., `python -m http.server 8000`.
* **Missing Data**: Ensure the dataset files are downloaded and placed in the correct directories.

---

## **License**

This project is licensed under the MIT License.

---

### **Additional Notes:**

* Replace the placeholder links for `train.csv`, `cleaned_trips.csv`, and `your-video-link` with the actual Google Drive and video URLs.
* Ensure the `requirements.txt` in the `backend/` directory contains the correct package versions:

  ```plaintext
  flask==2.3.2
  flask-cors==3.0.10
  mysql-connector-python==8.0.33
  gunicorn==20.1.0
  pandas==2.0.3
  ```

---

This README should provide a clear, user-friendly guide to setting up and running the project on Windows, macOS, and Ubuntu Linux. It includes all necessary steps, such as downloading datasets, installing dependencies, setting up MySQL, and running both the frontend and backend servers.

```

---

### **Key Improvements:**

- **Formatting**: Added headers and organized steps into clear sections.
- **Code blocks**: Properly formatted code snippets for easy copy-pasting.
- **Clear instructions**: Added more concise language and emphasized key steps with bold text for better readability.

You can now copy this and paste it directly into your GitHub repository!
```
