# Vehicle Price Evaluation

## **Project Overview**

The **Vehicle Price Evaluation** project aims to predict the prices of vehicles in Bulgaria based on their attributes, such as mileage, engine size, brand, and condition. This project involves scraping data from **auto.bg**, cleaning and preprocessing the data, and building machine learning models to make accurate price predictions. The ultimate goal is to provide insights that help car dealerships and buyers make informed decisions about vehicle pricing.

---

## **How the Project Works**

### **1. Data Collection**

The project begins with a **web scraper** that extracts car listings from **auto.bg**. The scraper:

-  Collects details such as the car's title, price, mileage, engine type, and other specifications.
-  Visits individual car detail pages to gather additional information.
-  Saves the scraped data into a CSV file (`auto_bg_cars.csv`) for further analysis.

The scraper is implemented using Python libraries such as `requests`, `BeautifulSoup`, and `pandas`. It avoids duplicate entries by checking existing data in the CSV file and skips already-scraped listings.

---

### **2. Data Understanding**

Once the data is collected, the next step is to explore and understand it:

-  Inspect the dataset structure, column names, and data types.
-  Identify key features such as `Mileage`, `Engine Size`, `Year`, and `Fuel Type`.
-  Check for missing values and outliers in the dataset.
-  Analyze relationships between features and the target variable (`Price`) using visualizations like scatter plots and correlation heatmaps.

---

### **3. Data Cleaning**

The data cleaning process ensures the dataset is consistent and ready for modeling:

-  **Removing Unnecessary Columns**: Drop irrelevant columns such as URLs and IDs.
-  **Renaming Columns**: Standardize column names for better readability.
-  **Handling Missing Values**: Fill missing values or drop rows with critical missing data.
-  **Cleaning Prices**: Remove unrealistic or empty price values.
-  **Extracting Relevant Details**:
   -  Extract the year from the `Manufactured` column.
   -  Extract the fuel type from the `Engine Type` column.
   -  Extract horsepower values from the `Power [hp]` column.
-  **Separating Brand and Model**: Split the `Model` column into `Brand` and `Model_Name` for better feature representation.

---

### **4. Data Preprocessing**

The cleaned data is transformed into a format suitable for machine learning:

-  **Encoding Categorical Variables**: Convert columns like `Fuel Type` and `Condition` into numerical values using `LabelEncoder`.
-  **Scaling Numerical Features**: Standardize numerical columns like `Mileage` and `Engine Size` using `StandardScaler`.
-  **Feature Engineering**:
   -  Create a `Car_Age` column by subtracting the manufactured year from the current year.
   -  Create a `Mileage_per_Year` column to normalize mileage based on the car's age.
-  **Outlier Removal**: Remove extreme values in `Price` and `Mileage` to improve model performance.

---

### **5. Data Visualization**

To better understand the data and validate the preprocessing steps, several visualizations are created:

-  **Price Distribution**: Analyze the spread of vehicle prices.
-  **Mileage vs. Price**: Visualize the relationship between mileage and price.
-  **Top Brands and Models**: Identify the most common brands and models in the dataset.
-  **Correlation Heatmap**: Highlight relationships between numerical features and the target variable.

---

### **6. Modeling**

The final step involves building and evaluating machine learning models to predict vehicle prices:

-  **Baseline Model**: A simple Linear Regression model is used as a baseline.
-  **Decision Tree Regressor**: Captures non-linear relationships in the data.
-  **Random Forest Regressor**: An ensemble model that combines multiple decision trees to improve accuracy and reduce overfitting.
-  **Hyperparameter Tuning**: Optimize model parameters (e.g., `max_depth`, `n_estimators`) to achieve the best performance.

Each model is evaluated using metrics such as:

-  **Mean Absolute Error (MAE)**: Measures the average prediction error.
-  **Mean Squared Error (MSE)**: Penalizes larger errors more heavily.
-  **R² Score**: Indicates how well the model explains the variance in the target variable.

---

## **How to Run the Project**

### **1. Prerequisites**

-  Python 3.8 or higher
-  Required libraries: `pandas`, `numpy`, `requests`, `BeautifulSoup`, `matplotlib`, `seaborn`, `scikit-learn`

### **2. Steps to Run**

1. Clone the repository:
   ```bash
   git clone https://git.fhict.nl/I546396/vehicle-price-evaluation.git
   cd vehicle-price-evaluation
   ```
