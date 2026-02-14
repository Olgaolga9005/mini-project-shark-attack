# mini-project-shark-attack
### Shark Attacks Data Analysis Project
### Project Overview
### This project presents a comprehensive data analysis of global shark attack incidents using Python in a Google Colab environment.
### The primary objective was to explore patterns in the shark attack dataset and determine whether the two formulated hypotheses could be confirmed or rejected:
### Hypothesis 1: According to the regular news, there are many shark attacks in Australia.
### Hypothesis 2: There are more shark attacks during the summer in Australia, with a higher number of fatal cases.
### To test these hypotheses, the analysis focused on the following data series:
### Frequency by country, with a focus on Australia\
### Temporal distribution and seasonality\
### Relationship between activity and fatal outcomes\

### The project combines data cleaning, exploratory data analysis (EDA), and structured interpretation of results to evaluate whether media perception aligns with statistical evidence.
### Dataset Description
### The dataset contains historical shark attack records including:

### Date of incident\
### Country\
### Activity provoked the attack\
### Fatal (Y/N/Unknown)\
### Additional contextual information

### The dataset required preprocessing due to inconsistent formatting and missing values.
### Data Cleaning and Preprocessing
### 1/ Date Standardization
### The Date column contained inconsistent formats such as mixed structures, partial dates, and invalid entries.

### All date values were standardized using:
df["Date_clean"] = pd.to_datetime(df["Date"], errors="coerce")

### Additional temporal features were extracted:
### df["Month"] = df["Date_clean"].dt.month

### df["Year"] = df["Date_clean"].dt.year

### This enabled the seasonal and yearly trend analysis.
### 2/ Fatality Column Cleaning
### The Fatal column was standardized into three categories:

### "Y" (Fatal)\
### "N" (Non-fatal)\
### "Unknown"

### This ensured usable value comparison.
### Country Filtering
### To focus on Australia:
### df_aus = df[df["Country"].str.strip().str.title() == "Australia"]
### Exploratory Data Analysis
### Country Comparison
### df["Country"].value_counts()
### Used to rank countries by total incidents and compare Australia to global totals.
### Temporal Distribution
### df_aus.groupby("Month").size().sort_index()

### Used to detect seasonal peaks and identify high‑risk months.
### Activity vs Fatal Outcomes
### pd.crosstab(df_aus["Activity"], df_aus["Fatal_clean"])
### Code Documentation Standards
### All custom functions include complete docstrings describing:

### Purpose\
### Parameters\
### Return values\
### Expected data types

### Example:
### def calculate_country_percentage(df, country_name):

    """
    Calculates the percentage of total shark attacks 
    corresponding to a specific country.

    Parameters:
        df (pd.DataFrame): The shark attack dataset.
        country_name (str): Country to filter.
    Returns:
        float: Percentage of total cases.

    """

### Clear and concise inline comments are included throughout the notebook to explain purpose and analytical logic.
### Tools Used
### Python 3\
### pandas\
### Google Collab
### Conclusion
### This project demonstrates structured data cleaning, exploratory analysis, and interpretation using Python.
### It provides evidence-based insights into global shark attack trends, with a focused evaluation of Australia and the activities resulting in fatal incidents.

>> Link to a presentation with Project overview and Insights on Google slides : https://docs.google.com/presentation/d/1FkuZNmrg_GSmBy-u2OHFJ58FQAyiSiw5YIhf6Lzk5gQ/edit?usp=sharing
