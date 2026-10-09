# Data Centers, Generation Capacity, and Electricity Prices in the U.S.

Natali Terreri & Vi Nguyen

## Background

**Research Question:** How is the location and concentration of data centers in the U.S. related to nearby electricity generation capacity and to retail electricity prices?

**Why it matters:** Data centers are one of the fastest-growing sources of electricity demand, driven by the rise of artificial intelligence. That growth directly affects the communities that neighbor these facilities, and policymakers are looking for solutions. The main concerns are:

- **Grid reliability:** whether the grid can keep up, and how much new generation capacity will be needed
- **Cost to ratepayers:** whether utility customers end up subsidizing infrastructure built for large tech loads
- **Environmental impact:** the cost of meeting that demand with fossil fuels

Combining data center records with federal energy data will let communities and policymakers see where data centers are concentrated, whether their growth is related to rising electricity prices, and how they affect the communities around them.

## Data Sources

| Source | Note | Limitations | Level |
|--------|------|-------------|-------|
| FracTracker Data Centers | Contains 1,694 rows with detailed information on data centers such as location information (address, lat/long, state & county), status, size ranking (categorical), power source, cooling source, property size, and even information on community sentiment. | Many columns are empty for many rows, limiting the value of the available data. | Facility (point location, with lat/long, state, and county) |
| EIA Electricity Sales to Ultimate Customers | This data set is a simple table of monthly average electricity prices broken down by state, and customer type. It includes price, number of customers, and volume of sales in million kilowatt hours. This data is available via API. | Prices are reported only at the state level, which can hide differences between utilities and counties. | State × month × customer type (residential, commercial, industrial) |
| EIA Annual Electric Generator Report | This data set contains "generator-level specific information about existing and planned generators and associated environmental equipment at electric power plants." | This data set is very robust including multiple tables of different data. In total, the dataset contains over 300 variables including plant location, name, utility name, primary sector, fuel source, status, and maximum generation capacity. | Generator |

## Methods

This project uses exploratory data analysis at two levels. The first is a state-by-year analysis over time, comparing the growth of data centers and power generators with changes in electricity sales and prices. This first stage will uncover outlier states. For example, those with a high concentration of data centers, high electricity prices, or rapid growth in generation capacity. We will then filter the data to these outlier states and carry out the second level, a state-level cross-sectional analysis comparing their data centers, electricity prices, and generation capacity.

**Outcomes:**
- Average retail electricity price by state, year, and customer type
- Retail electricity sales: year over year percent change
- Data center concentration and growth

**Comparison groups:**
- High- vs. low-data-center states
- High vs. low energy cost states
- Data center size
- Energy source

### Analysis Steps

1. Create Data Dictionary
2. Import files to Project. Create Data Frames for main data sources (Data Centers, Electricity Use by Customer, Energy Generator). Add operable and planned generators to the same dataframe.
3. Clean Data: replace or delete any NaN data, adjust categorical data to be more useful, and any other changes including data types or string cleaning.
4. Create Data Frame for Summary of Electricity Generators: summarize generators by type and capacity, and number of generators by status (operable & proposed).
5. Create Data Frame for Data Center Summary by State.
6. Create Data Frame for Electricity Use by State & Year: create Year column, group by Electricity Use, State, and Year.
7. Join Electricity Use by State & Year with Electricity Generators, matching key on state.
8. Filter Electricity Use and Electricity Generators to 3-5 highest and lowest data center states.

## Key Findings

- [Finding 1]
- [Finding 2]
- [Finding 3]

## Repository Structure

| File | Description |
|------|-------------|
| `Python_Data_Centers_Nguyen_Terreri.ipynb` | Main analysis notebook |
| `clean_datacenters.ipynb` | Cleans the raw data center dataset (e.g., zip code formatting) |
| `datacenters_clean.csv` | Cleaned data center locations, capacity (MW), status, and operators |
| `EIA_Plant_Y2025.csv` | EIA power plant data, 2025 |
| `EIA_Generator_Y2025_Current.csv` | EIA operating generators, 2025 |
| `EIA_Generator_Y2025_Proposed.csv` | EIA proposed generators, 2025 |
| `EIA_Generator_Y2025_Retired.csv` | EIA retired generators, 2025 |
| `annual_electricity_usage_15-25.csv` | Annual electricity usage, 2015–2025 |
