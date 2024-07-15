# Population Data Visualization

This repository contains a script to visualize the distribution of populations across countries using a bar chart. The dataset used is from the World Bank and contains population data by country.

## Dataset

The dataset used for this visualization can be found at: [World Bank Population Data](https://data.worldbank.org/indicator/SP.POP.TOTL)

## Requirements

To run the script, you will need the following Python libraries:
- pandas
- matplotlib

You can install these libraries using pip:
```
pip install pandas matplotlib
```

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

## Output

The script will display a bar chart showing the top 10 countries by population for the latest available year in the dataset.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
