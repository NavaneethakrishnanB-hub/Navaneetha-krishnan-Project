NSL-KDD Intrusion Detection Dataset – Data Analysis Project

This project performs exploratory data analysis (EDA) and data cleaning on the NSL-KDD dataset, a well-known benchmark dataset used for network intrusion detection systems (IDS).
The analysis is done entirely in Google Colab using Python and Pandas.


---

📌 Project Objectives

Load and inspect the NSL-KDD dataset.

Understand dataset structure, columns, and label distribution.

Check and clean missing values, duplicates, and column formatting.

Generate descriptive statistics for all numerical features.

Prepare the dataset for future machine learning tasks.



---

📥 Dataset Used

File used:

nsl_kdd_dataset.csv

Dataset Info:

Rows: 4430

Columns: 42

Label column: label

Attack Types:

normal

DoS

U2R

R2L



All data features are normalized between 0 and 1.


---

🧪 Steps Performed in Analysis

1. Loading the Dataset

Uploaded via Google Colab using:

from google.colab import files
uploaded = files.upload()
data = pd.read_csv('nsl_kdd_dataset.csv')
df = pd.DataFrame(data)

2. Viewing the Dataset

df.head() – First 5 records

df.tail() – Last 5 records

Verified all columns and sample label values.


3. Column Cleanup

df.columns = df.columns.str.strip()

Ensures there are no unwanted whitespaces in column names.


---

🔍 Data Quality Checks

✔ Missing Values

df.isnull().sum()

Result:
➡ 0 missing values in all 42 columns

✔ Duplicate Rows

df.duplicated().sum()

Result:
➡ 0 duplicate rows

Dataset is already clean and consistent.


---

📊 Descriptive Statistics

Generated using:

df.describe()

Observations:

Most values range from 0.0002 to 0.9999

Mean of features ≈ 0.49 – 0.50

Standard deviation ≈ 0.28 – 0.29

Dataset is uniformly normalized.



---

🔢 Example Analysis

Converted a column to numeric and calculated mean:

df['src_bytes'] = pd.to_numeric(df['src_bytes'], errors='coerce')
df['src_bytes'].mean()

Mean src_bytes: ≈ 0.5069


---

🛡 Attack Categories (Label Column)

The dataset includes the following traffic types:

normal – Legitimate network traffic

DoS – Denial of Service

U2R – User to Root attack

R2L – Remote to Local attack


These labels are essential for intrusion classification tasks.


---

🧹 Final Cleaned Dataset

After cleaning:

No missing values

No duplicates

Column names standardized

All numeric fields properly parsed

Dataset ready for ML



---

🚀 Future Work

Build ML models (Logistic Regression, Random Forest, SVM, etc.)

Visualize attack distributions

Create an Intrusion Detection System model

Evaluate model with accuracy, precision, recall, F1-score



---

🛠 Technologies Used

Python

Google Colab

Pandas

NumPy
