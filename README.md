# Global Terrorism Analysis

## Introduction

In this project, we prepare and analyze The Global Terrorism Dataset to extract insightful information. We compare the performance of the Dask library with Pandas, focusing on memory usage and efficiency.

## Dataset

The Global Terrorism Database (GTD) is a publicly accessible dataset that catalogs information on terrorist attacks worldwide from 1970 to 2017. It includes data on both domestic and international incidents, with over 180,000 attacks recorded during this period. The dataset contains 135 columns and 181,691 rows.

## Data Preprocessing and Cleansing

### Exploration

The dataset contains many columns with null values. For our analysis, we selected the following columns:
- Year
- Month
- Day
- Country
- Region
- City
- State
- Latitude
- Longitude
- Success
- Suicide
- AttackType
- Killed
- Wounded
- Casualties
- Target
- Group
- Target_type
- Weapon_type

### Cleaning

We addressed missing values as follows:
- **City, State, Target**: Replaced nulls with "Unknown".
- **Killed, Wounded, Casualties**: Replaced nulls with 0.
- **Latitude, Longitude**: Calculated mean values by region and filled missing data based on these means.

Duplicates were checked and none were found.

## Data Analysis

Basic statistical analysis was performed using NumPy to summarize the dataset. We calculated the mean, median, and standard deviation for the columns: Killed, Wounded, and Casualties.

## Data Visualizations

Visualizations were created to better understand the trends and patterns in the data.

## Performance Comparison with Dask

We tested Dask with 5 partitions and compared its performance with NumPy. Despite similar memory usage, NumPy outperformed Dask for our dataset. Increasing the number of partitions in Dask did not improve performance and instead slowed down processing. This may be due to the relatively small size of our dataset, where Dask's overhead in managing partitions outweighed the benefits of parallel processing. Dask is generally more beneficial for larger datasets that can leverage distributed computing for performance gains.

## Challenges During Analysis

- **Column Selection**: Navigating the extensive number of columns and selecting relevant ones for analysis required significant effort and time.
- **Handling Missing Data**: Effectively managing null values was crucial to avoid bias and ensure accurate analysis results.

## Files Included

- **`Global Terrorism Report.pdf`**: A detailed report on the analysis and findings.
- **`Global Terrorism.ipynb`**: Jupyter Notebook containing the code for data processing, analysis, and visualization.
- **`globalterrorism-cleaned.rar`**: Compressed file containing the cleaned dataset.
