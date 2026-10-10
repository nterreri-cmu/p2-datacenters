# Data Dictionary 
###for data sources and key variables used in analysis

## FracTracker Database (datacenters_clean.csv)

| Name | Type | Description |
|------|------|-------------|
| facility_name | string | Name of the facility |
| address | string | Street address of facility |
| city | string | City of facility location |
| state | string | State of facility |
| zip | string | Zip code of facility location |
| county | string | County of facility location |
| lat | float | Latitude |
| lon | float | Longitude |
| status | string | Status of facility. Values include "Operating", "Approved/Permitted/Under construction", "Proposed" |
| operator_name | string | Name of facility operator |
| sizerank | string | Categorical variable of estimated size of the facility |
| status_group | string | Grouped and cleaned value based on status |


## Generator

# Data Dictionary: EIA Generator Data

## EIA Generator Inventory (EIA_Generator_Y2025_Current.csv and EIA_Generator_Y2025_Proposed.csv)

Each row is one generator at one power plant. Blank cells mean the field doesn't apply.

| Name | Type | Description |
|------|------|-------------|
| Utility ID | integer | EIA-assigned identifier for the utility |
| Utility Name | string | Name of the utility that owns or operates the plant |
| Plant Code | integer | EIA-assigned identifier for the plant |
| Plant Name | string | Name of the plant |
| State | string | Two-letter state abbreviation |
| County | string | County where the plant is located |
| Generator ID | string | Generator identifier within the plant (mixed values like "1", "5.1", "WT1") |
| Unit Code | string | Code identifying the unit the generator belongs to (e.g., a combined-cycle unit) |
| Technology | string | Generating technology (e.g., "Petroleum Liquids", "Onshore Wind Turbine", "Conventional Hydroelectric") |
| Prime Mover | string (code) | Prime mover type code (e.g., IC = internal combustion, ST = steam turbine, HY = hydraulic turbine, WT = wind turbine) |
| Ownership | string (code) | Ownership type (e.g., S = single owner, J = jointly owned) |


## Electricity Analysis

## EIA Retail Sales of Electricity (annual_electricity_usage_15-25.csv)

Each row is one state and one customer sector for one year.

### Identification

| Name | Type | Description |
|------|------|-------------|
| period | integer | Reporting period (year in this sample, e.g., 2025) |
| stateid | string | Two-letter state abbreviation |
| stateDescription | string | Full state name |
| sectorid | string (code) | Customer sector code: ALL = all sectors, COM = commercial, IND = industrial, OTH = other, RES = residential, TRA = transportation |
| sectorName | string | Descriptive name of the customer sector |

### Measures

| Name | Type | Description |
|------|------|-------------|
| customers | integer | Number of customers (electric service accounts) in the state and sector |
| price | float | Average retail price of electricity, in cents per kilowatt-hour |
| revenue | float | Total revenue from electricity sales, in million dollars |
| sales | float | Total electricity sold, in million kilowatt-hours |

### Units

| Name | Type | Description |
|------|------|-------------|
| customers-units | string | Unit label for `customers` ("number of customers") |
| price-units | string | Unit label for `price` ("cents per kilowatt-hour") |
| revenue-units | string | Unit label for `revenue` ("million dollars") |
| sales-units | string | Unit label for `sales` ("million kilowatt hours") |
