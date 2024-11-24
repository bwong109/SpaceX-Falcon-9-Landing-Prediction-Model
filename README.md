
# SpaceX Falcon 9 First Stage Landing Prediction

## Project Overview

This project predicts the success of SpaceX Falcon 9 first-stage booster landings using supervised machine learning techniques. It involves web scraping launch data from Wikipedia, data preprocessing, exploratory data analysis, feature engineering, and building multiple machine learning models to evaluate their performance.

---

## Key Steps and Methodology

### 1. **Web Scraping SpaceX Launch Data**
   - **Objective:** Extract data from the [Wikipedia Falcon 9 Launch List](https://en.wikipedia.org/wiki/List_of_Falcon_9_and_Falcon_Heavy_launches).
   - **Tools Used:** 
     - `BeautifulSoup` for parsing HTML.
     - `requests` for HTTP requests.
   - **Data Extracted:**
     - Flight number
     - Launch site
     - Payload information
     - Orbit type
     - Customer
     - Booster version
     - Launch outcome

   The extracted data was stored in a structured format using a Python dictionary and converted into a pandas DataFrame.

---

### 2. **Data Preprocessing**
   - Cleaned and normalized payload mass and booster version data.
   - Processed categorical outcomes (e.g., `True ASDS`, `False Ocean`) into binary labels: `1` for success, `0` for failure.
   - Imputed missing values and ensured consistent data types.

---

### 3. **Exploratory Data Analysis (EDA)**
   - **Techniques:**
     - Aggregated and visualized launch success rates by site and orbit.
     - Analyzed trends between payload mass, flight numbers, and success rates.
   - **Findings:**
     - Higher flight numbers are correlated with higher landing success rates.
     - Payload mass impacts landing outcomes, with heavier payloads often failing.
     - Launch site success rates vary:
       - **CCAFS LC-40**: ~60%
       - **KSC LC-39A**: ~77%
       - **VAFB SLC-4E**: ~77%

---

### 4. **Feature Engineering**
   - Created one-hot encoded features for categorical variables such as `Orbit`, `Launch Site`, and `Booster Version`.
   - Standardized numerical features like `PayloadMass` and `FlightNumber` for consistent scaling.

---

### 5. **Machine Learning Models**
   - Evaluated multiple models to predict landing success:
     - Logistic Regression
     - Support Vector Machines (SVM)
     - Decision Trees
     - K-Nearest Neighbors (KNN)
   - **Model Selection:**
     - Used `GridSearchCV` for hyperparameter tuning.
     - Performed cross-validation with 10 folds to evaluate accuracy.
   - **Performance:**
     - Logistic Regression: 83.3% accuracy
     - SVM: 83.3% accuracy
     - Decision Tree: 83.3% accuracy
     - KNN: 83.3% accuracy
   - **Confusion Matrix:**
     - Models showed good performance, though false positives were a challenge.

---

## Tools and Libraries
- **Web Scraping:** `BeautifulSoup`, `requests`
- **Data Handling:** `pandas`, `numpy`
- **Visualization:** `matplotlib`, `seaborn`
- **SQL for EDA:** `sqlite3`, `SQLAlchemy`
- **Machine Learning:** `scikit-learn`

---

## Results and Insights
- Feature importance analysis highlighted that:
  - Flight number and payload mass significantly influence landing success.
  - Orbit types like `GTO` and `ISS` show distinct success rates.
- Models trained and tested on the dataset achieved ~83% accuracy, indicating reliable performance for landing predictions.

---

## How to Run the Code
1. Clone or download the repository.
2. Install required libraries:
   ```bash
   pip install beautifulsoup4 requests pandas numpy matplotlib seaborn scikit-learn sqlalchemy
   ```
3. Run the Jupyter notebook or Python script sequentially.

---

## Future Improvements
- Expand the dataset with newer Falcon 9 launches.
- Incorporate weather data and launch conditions to improve prediction accuracy.
- Experiment with deep learning models for better feature representation.

---

## Author
- **Name:** Brian Wong
- **Affiliation:** Data Science Enthusiast, Space Enthusiast
