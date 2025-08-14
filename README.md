# Space-X-Falcon-9-Landing-Prediction

Developed and deployed a full-stack data science pipeline to predict the success of SpaceX Falcon 9 first-stage landings using historical mission data.

# Data Science Project Overview

This repository contains Python scripts, SQL queries, and interactive dashboards that together form a complete data workflow — from data acquisition to predictive modeling.  
It provides a hands-on understanding of **data engineering, exploratory data analysis, visualization, and machine learning** applied to a real-world aerospace dataset.

## Files

### 1. `scripts/fetch_spacex.py`
Fetches and compiles SpaceX launch data from multiple sources:
- **API Integration**: SpaceX REST API v4, NASA Open API.
- **Data Aggregation**: Combines rockets, payloads, launchpads, and cores data.
- **Feature Engineering**: Payload mass, orbit, landing outcome class.

Use this script to automatically retrieve the latest SpaceX launch data.

---

### 2. `scripts/wrangle.py`
Cleans and preprocesses the raw dataset:
- **Missing Data Handling**: Imputation and default values.
- **Feature Normalization**: Scaling and encoding.
- **Database Integration**: Stores cleaned data into a SQLite database.

This script prepares the dataset for both analysis and modeling.

---

### 3. `scripts/sql_insights.py`
Executes SQL queries on the processed dataset to extract key insights:
- Unique launch sites.
- Payload statistics by mission type.
- First successful ground pad landing.
- Mission success and failure counts.

Outputs results as CSV files in `reports/figures/`.

---

### 4. `scripts/eda_plots.py`
Generates exploratory data analysis visualizations:
- **Success Rate by Orbit Type**
- **Payload Distribution by Launch Site**
- **Yearly Success Trends**

Saves static charts to `reports/figures/`.

---

### 5. `scripts/map_folium.py`
Creates an interactive launch site map:
- **Marker Size**: Proportional to number of launches.
- **Color Coding**: Green for high success rate, red for low.
- **Popups**: Show site details and statistics.

Outputs `reports/maps/launch_sites.html`.

---

### 6. `models/train.py`
Trains machine learning models to predict landing outcomes:
- **Algorithms**: Logistic Regression, SVM, Decision Tree.
- **Pipeline**: Preprocessing with scaling and one-hot encoding.
- **Model Selection**: Hyperparameter tuning with GridSearchCV.
- **Evaluation**: Accuracy, F1-score, confusion matrix.

Saves the best model as `models/best_model.joblib`.

---

### 7. `app/app_dash.py`
Interactive dashboard built with Plotly Dash:
- **Dropdown**: Select a launch site.
- **Range Slider**: Filter by payload mass.
- **Visualizations**: Outcome pie chart and payload vs. success scatter plot.

---

## Requirements
Before running the code, install dependencies:
```bash
pip install -r requirements.txt
```

## Usage
1. Clone this repository:
   ```bash
   git clone https://github.com/gannavarapu-priya/Space-X-Falcon-9-Landing-Prediction.git
   cd Space-X-Falcon-9-Landing-Prediction
   ```
2. Run the full pipeline:
   ```bash
   python main.py
   ```
3. Launch the interactive dashboard:
   ```bash
   python app/app_dash.py
   ```
4. View generated outputs.

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your enhancements.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contact
For questions or collaboration, feel free to reach out at gannavarapup.11@gmail.com.

---

Happy coding and learning!
