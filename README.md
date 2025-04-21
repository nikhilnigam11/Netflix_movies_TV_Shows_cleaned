# Netflix_movies_TV_Shows_cleaned
Netflix_movies_TV_Shows_cleaned  
Day 1 task Elevate Labs
Date : 21 April 2025
Steps Completed

**1. Libraries Imported**
pandas, numpy, matplotlib.pyplot, seaborn for data analysis and visualization.

**2. Dataset Overview**
Loaded dataset from CSV (df = pd.read_csv(...))
Displayed structure using df.head(), df.shape, and df.info()
Found: 8807 rows × 12 columns

**3. Missing Values Handled**
Displayed missing value counts and percentages
Key columns with missing data:
director (~30%)
cast (~9%)
country, date_added, rating, duration (few %)

**Action taken**:
Dropped rows where date_added, rating, and duration were missing
Filled:
'director' with "Director Name Not Provided"
'cast' with "Name Not Provided"
'country' with "Country Name Not Provided"

**4. String Cleanup & Transformation**
Removed extra spaces from date_added using .str.strip()
Converted release_year (from string) to proper datetime → then extracted just the year
Converted date_added to datetime64 format

**5. Handling Comma-Separated Values**
Used .str.split(',') and .explode() to:
Break down multi-valued entries in:
director, cast, listed_in, country
Then used .str.strip() to clean whitespace

**6. Removed Duplicates**
Checked with df.duplicated()
Found and dropped 10 duplicate rows

**7. Post-Cleaning Checks**
Rechecked missing values 
Sampled 10 random entries with df.sample(10)
