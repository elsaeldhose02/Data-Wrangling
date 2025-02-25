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


# Data-Wrangling
!pip install pandas
!pip install matplotlib

import pandas as pd

# Load the dataset directly from the URL
file_path = "https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/VYPrOu0Vs3I0hKLLjiPGrA/survey-data-with-duplicate.csv"
df = pd.read_csv(file_path)

df = pd.read_csv("https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/n01PQ9pSmiRX6520flujwQ/survey-data.csv")
df


# Display the first few rows
print(df.head())

# No. of duplicate values

duplicate = df.duplicated().sum()
duplicate
print(f"Number of duplicate rows: {duplicate}")

# Identify and display the first few duplicate rows (including the first occurrence)
duplicate_rows = df[df.duplicated(keep=False)]  # keep=False includes all occurrences
duplicate_rows

# Identify duplicate rows based on selected columns such as MainBranch, Employment, and RemoteWork. 
duplicate_rows = df[df.duplicated(subset=['MainBranch', 'Employment', 'RemoteWork'], keep=False)]
duplicate_rows

# Identify duplicate rows based on selected columns: 'MainBranch', 'Employment', 'RemoteWork'
duplicate_rows = df[df.duplicated(subset=['MainBranch', 'Employment', 'RemoteWork'], keep=False)]

# Display the first few duplicate rows to understand their structure
print("First few duplicate rows based on selected columns:")
print(duplicate_rows.head())

# Now, analyze which columns contain identical values in the duplicate rows
# Count the number of duplicates in each of the selected columns
duplicate_columns = ['MainBranch', 'Employment', 'RemoteWork']

for column in duplicate_columns:
    duplicate_value_count = duplicate_rows[column].value_counts()
    print(f"\nValue counts for {column} in duplicate rows:")
    print(duplicate_value_count)

# Plot distribution of duplicates for 'MainBranch'
plt.figure(figsize=(8, 6))
mainbranch_counts = duplicate_rows['MainBranch'].value_counts()
plt.bar(mainbranch_counts.index, mainbranch_counts.values, color='skyblue')
plt.title('Distribution of Duplicates across MainBranch')
plt.xlabel('MainBranch')
plt.ylabel('Count of Duplicates')
plt.xticks(rotation=90)
plt.show()

# Plot distribution of duplicates for 'Employment'
plt.figure(figsize=(8, 6))
employment_counts = duplicate_rows['Employment'].value_counts()
plt.bar(employment_counts.index, employment_counts.values, color='lightgreen')
plt.title('Distribution of Duplicates across Employment')
plt.xlabel('Employment')
plt.ylabel('Count of Duplicates')
plt.xticks(rotation=45)
plt.show()

# Plot distribution of duplicates for 'RemoteWork'
plt.figure(figsize=(8, 6))
remotework_counts = duplicate_rows['RemoteWork'].value_counts()
plt.bar(remotework_counts.index, remotework_counts.values, color='salmon')
plt.title('Distribution of Duplicates across RemoteWork')
plt.xlabel('RemoteWork')
plt.ylabel('Count of Duplicates')
plt.xticks(rotation=45)
plt.show()


print("First few duplicate rows based on subset columns:")
print(duplicate_subset.head(5))

# To focus on columns that have identical values, we can filter those with only 1 unique value in the group
identical _columns= duplicates_grouped[duplicates_grouped == 1].dropna(axis=1, how='all')
identical _columns
