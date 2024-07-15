# Population Data Visualization

This repository contains a script to visualize the distribution of populations across countries using a bar chart. The dataset used is from the World Bank and contains population data by country.

## Dataset

The dataset used for this visualization can be found at: [World Bank Population Data](https://data.worldbank.org/indicator/SP.POP.TOTL)

## Requirements

To run the script, you will need the following Python libraries:
- pandas
- matplotlib

You can install these libraries using pip:
pip install pandas matplotlib

## Script Description

The script performs the following steps:
1. Loads the population data from a CSV file.
2. Filters the data for the latest available year.
3. Sorts the data by population in descending order.
4. Selects the top 10 countries by population.
5. Creates a bar chart to visualize the population of these top 10 countries.

## How to Run

1. **Download the Dataset:**
   Download the population data CSV file from the World Bank website and save it as `population.csv`.

2. **Place the CSV File:**
   Place the `population.csv` file in the same directory as the script.

3. **Run the Script:**
   Execute the script to generate the bar chart.
   
   ```python
   import pandas as pd
   import matplotlib.pyplot as plt

   # Load the data from the uploaded CSV file
   file_path = 'population.csv'
   population_data = pd.read_csv(file_path, skiprows=4)

   # Display the first few rows of the dataframe to understand its structure
   print("First few rows of the dataset:")
   print(population_data.head())

   # Display the columns to check the latest year column
   print("Columns in the dataset:")
   print(population_data.columns)

   # Filter the data for the latest year available
   latest_year = population_data.columns[-2]  # Ensure you are selecting the correct column
   print(f"Latest year column: {latest_year}")

   # Filter data for the latest year
   population_latest = population_data[['Country Name', latest_year]].dropna()

   # Rename the columns for easier access
   population_latest.columns = ['Country', 'Population']

   # Convert Population to numeric (if not already)
   population_latest['Population'] = pd.to_numeric(population_latest['Population'], errors='coerce')

   # Check if the Population column has been converted correctly
   print("Data types after conversion:")
   print(population_latest.dtypes)

   # Display the first few rows of the latest population data to check the values
   print("First few rows of the latest population data:")
   print(population_latest.head())

   # Sort the data by population in descending order
   population_latest = population_latest.sort_values(by='Population', ascending=False)

   # Select the top 10 countries by population for the bar chart
   top_10_population = population_latest.head(10)
   print("Top 10 countries by population:")
   print(top_10_population)

   # Create the bar chart
   plt.figure(figsize=(10, 6))
   plt.bar(top_10_population['Country'], top_10_population['Population'], color='lightblue')
   plt.xlabel('Country')
   plt.ylabel('Population')
   plt.title('Top 10 Countries by Population')
   plt.xticks(rotation=45)
   plt.tight_layout()

   # Show the plot
   plt.show()
   ```

## Output

The script will display a bar chart showing the top 10 countries by population for the latest available year in the dataset.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
