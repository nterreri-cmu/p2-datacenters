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

## EIA Generator Inventory (filename.csv)

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



| Name | Type | Description |
|------|------|-------------|
