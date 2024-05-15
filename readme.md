## Project Background

This project aims to analyze the relationship between the proportion of low-income occupations and fuel poverty in the Leeds area. Fuel poverty is an issue that affects many households. Understanding its relationship with types of occupations can help implement more effective interventions. By generating an index related to the proportion of low-income occupations and fuel poverty and using K-means clustering, we will visualize the relationship both spatially and non-spatially.

## Data Sources

1. **Occupation Data:** This dataset contains information on the types of occupations of Leeds residents, categorized into different occupation types.
   - File: `census2021_ts063_lsoa.csv`
   - Source: [Nomis Official Labour Market Statistics](https://www.nomisweb.co.uk/sources/census_2021_bulk)

2. **Fuel Poverty Data:** This dataset includes the number and proportion of households experiencing fuel poverty within different LSOAs.
   - File: `Fuel_poverty_by_LSOA.csv`
   - Source: [Data Mill North](https://datamillnorth.org/dataset/2j70l/fuel-poverty-by-lsoa-england)

3. **Leeds Geospatial Data:** This GeoJSON file provides the geographic boundaries of Leeds LSOAs, used for spatial visualization of analysis results.
   - File: `Leeds.geojson`
   - Source: [Francesca Pontin's GitHub](https://github.com/FrancescaPontin/GEOG5990M/tree/main/data/week_20)

## Purpose of the Code

The main purpose of the code is to integrate occupation data and fuel poverty data, analyze the relationship between the two, and present the results through spatial and non-spatial visualizations. The analysis involves the following steps:

1. **Data Loading and Cleaning:**
   Load the occupation and fuel poverty data, filter the data to include only Leeds, and remove missing or invalid data.

2. **Calculate the Proportion of Low-Income Occupations:**
   Calculate the proportion of low-income occupations in each LSOA. Sales and customer service, craft, plant and machine operators, and elementary occupations are defined as low-income occupations.

3. **Create and Normalize a New Index:**
   Merge the occupation data and fuel poverty data, create a new index representing the combined effect of low-income occupation proportion and fuel poverty proportion, and normalize the index to a range of 0-1.

4. **K-means Clustering:**
   Use K-means to classify LSOAs into three categories based on the calculated low-income occupation proportion and fuel poverty proportion, and visualize the clustering results using a scatter plot.

5. **Spatial Visualization:**
   Combine the analysis results with geospatial data and create three maps representing the spatial distribution of the normalized index, low-income occupation proportion, and fuel poverty proportion, respectively.

## GitHub Repository Contents

### Data:
- `census2021_ts063_lsoa.csv`: Occupation data file.
- `Fuel_poverty_by_LSOA.csv`: Fuel poverty data file.
- `Leeds.geojson`: Geospatial data file for Leeds.

### Code:
- `201746746.ipynb`: Jupyter Notebook containing the complete analysis code, from data loading and cleaning to visualization.

### Documentation:
- `readme.md`: This file, providing an overview of the project, data sources, purpose of the code, and instructions for running the analysis.

## Instructions for Running the Code

1. Open a new Notebook in Google Colab.
2. Clone the repository and use pip to install the required Python packages:
   ```
   !pip install pandas geopandas matplotlib seaborn scikit-learn
   ```
3. Use the file upload feature to upload all data files.
4. Run `201746746.ipynb` in Colab.
5. GitHub Link: (https://github.com/pppppppxiansen/201746746python)

## Results Analysis

### Non-spatial Visualization:
- The data is divided into three different clusters, with the proportion of low-income occupations and low fuel poverty proportion gradually increasing from cluster 0 to cluster 2.
- The scatter plot clearly shows a positive correlation between low-income occupation proportion and fuel poverty proportion. Areas with a higher proportion of low-income occupations have a higher fuel poverty proportion, indicating that low-income occupational groups are more likely to face fuel poverty.

### Spatial Visualization:
- The normalized index is represented by a color gradient from purple to yellow, indicating low to high values. High index areas are concentrated in the city center and certain specific areas, while low index areas are distributed in the suburbs.
- Areas with a high proportion of low-income occupations are concentrated in the city center, while lower proportions are found in the suburbs.
- Areas with a high fuel poverty proportion are concentrated in the city center, while lower proportions are found in the suburbs.
- Overall, the city center has the most severe issues of poverty and fuel poverty.