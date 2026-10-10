# Data Centers, Generation Capacity, and Electricity Prices in the U.S.

Natali Terreri & Vi Nguyen

## Research Question

How is the location and concentration of data centers in the U.S. related to nearby electricity generation capacity and to retail electricity prices?

## Why It Matters

Data centers are one of the fastest-growing sources of electricity demand, driven by the rise of artificial intelligence. That growth directly affects the communities that neighbor these facilities, and policymakers are looking for solutions. The main concerns are:

- **Grid reliability:** whether the grid can keep up, and how much new generation capacity will be needed
- **Cost to ratepayers:** whether utility customers end up subsidizing infrastructure built for large tech loads
- **Environmental impact:** the cost of meeting that demand with fossil fuels

## Data Sources

| Source | Description | Level |
|--------|-------------|-------|
| [FracTracker Alliance Data Centers](https://www.fractracker.org/) (2025) | 1,694 facilities with location (address, lat/long, state, county), status, size ranking, power and cooling source, and community sentiment. Many fields are sparsely populated. | Facility |
| EIA Electricity Sales to Ultimate Customers (2026a) | Annual electricity sales, prices, and number of customers by state and customer type (residential, commercial, industrial), 2016–2025. Prices are reported only at the state level, which can hide differences between utilities and counties. | State × year × customer type |
| EIA Annual Electric Generator Report (2026b) | Generator-level data on capacity, fuel source, location, and status (operating, proposed, retired). | Generator |

## Methods

All analysis was done in Python using **pandas**, **Matplotlib**, and **seaborn**, at the state level.

1. **Identify top data center states.** Counted data centers per state from the FracTracker database and selected the six states with the most facilities: **Virginia, Texas, Georgia, Pennsylvania, Ohio, and California**. These states are compared against the rest of the country throughout.
2. **Electricity demand.** Totaled annual EIA sales by state and year, calculated the percent change in sales from 2016 to 2025, and compared each top state's growth with the U.S. average, including a breakdown by customer type.
3. **Electricity prices.** Tracked average residential retail prices over time in the top six states.
4. **Generation capacity.** Summed operating and planned capacity from the EIA generator report and calculated planned capacity as a percentage of each state's current operating capacity.
5. **Combined analysis.** Built scatter plots comparing each state's number of data centers with its number of power generators (current and proposed) and its electricity sales, highlighting the six top data center states.

> **Note:** This analysis is descriptive. It shows how data center concentration relates to electricity demand, supply, and prices. 

## Key Findings

- **Data centers are highly concentrated.** States average 12 operating and 20 planned data centers, but the distribution is right-skewed. Virginia leads with 214 operating facilities, while some states have none.
- **Demand is growing fastest in data center states.** U.S. electricity sales reached a period high of 4.06 million GWh in 2025, up 7.9% since 2016. Growth was concentrated in the commercial sector and in data center states such as Texas (+30.4%) and Virginia (+28.9%). Most of the top six states far exceeded or came close to the national growth rate.
- **Commercial growth stands out.** Commercial and residential customers account for the largest shares of sales in the top states. Commercial growth is notable because data centers are typically billed as commercial customers.
- **Residential prices are rising.** Residential electricity prices rose in each of the six states with the most data centers.
- **Planned generation doesn't always match demand.** Texas plans to expand capacity by 53%, while Virginia, home to the most data centers, plans only 24% growth despite demand rising nearly 29%.

## Repository Structure

| File | Description |
|------|-------------|
| `UPDATE THIS` | Main analysis notebook |
| `clean_datacenters.ipynb` | Cleans the raw data center dataset|
| `datacenters_clean.csv` | Cleaned data center locations|
| `EIA_Plant_Y2025.csv` | EIA power plant data, 2025 |
| `EIA_Generator_Y2025_Current.csv` | EIA operating generators, 2025 |
| `EIA_Generator_Y2025_Proposed.csv` | EIA proposed generators, 2025 |
| `EIA_Generator_Y2025_Retired.csv` | EIA retired generators, 2025 |
| `annual_electricity_usage_15-25.csv` | Annual electricity sales, prices, and customers by state and customer type |

## References

- FracTracker Alliance. (2025). *Data centers database.*
- U.S. Energy Information Administration. (2026a). *Electricity sales to ultimate customers.*
- U.S. Energy Information Administration. (2026b). *Annual electric generator report (Form EIA-860).*
