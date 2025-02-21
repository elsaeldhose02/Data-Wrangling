# Data-Wrangling
!pip install pandas
!pip install matplotlib

import pandas as pd

# Load the dataset directly from the URL
file_path = "https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/VYPrOu0Vs3I0hKLLjiPGrA/survey-data-with-duplicate.csv"
df = pd.read_csv(file_path)

# Display the first few rows
print(df.head())

# No. of duplicate values

duplicate = df.duplicated().sum()
duplicate
print(f"Number of duplicate rows: {duplicate}")

# Display few duplicates

duplicate_rows = df[df.duplicated()]
duplicate_rows
print(duplicate_rows.head(2))

duplicate_rows = df[df.duplicated()]
duplicate_rows
print(duplicate_rows.head(2))

# Display the first few duplicate rows to understand their structure
print("First few duplicate rows based on subset columns:")
print(duplicate_subset.head())

# Identify duplicates based on selected columns ('MainBranch', 'Employment', 'RemoteWork')
duplicate_subset = df[df.duplicated(subset=['MainBranch', 'Employment', 'RemoteWork'], keep=False)]
duplicate_subset

print("First few duplicate rows based on subset columns:")
print(duplicate_subset.head(5))

# To focus on columns that have identical values, we can filter those with only 1 unique value in the group
identical _columns= duplicates_grouped[duplicates_grouped == 1].dropna(axis=1, how='all')
identical _columns
