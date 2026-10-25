# Uber Trip Insights Dashboard — Data Dictionary

## Scope

The supplied data covers **103,728 Uber trips** in New York City from **June 1 through June 30, 2024**. The source files are Excel workbooks stored in the `Dataset/` folder.

## Trip Details

Source: `Dataset/Uber Trip Details.xlsx`  
Sheet/table: `Trip Details` / `Table1`

| Column | Source type | Meaning |
|---|---|---|
| `Trip ID` | Whole number | Unique trip identifier. Use count or distinct count for trip volume; do not sum as a business KPI. |
| `Pickup Time` | Date/time | Trip pickup timestamp. |
| `Drop Off Time` | Date/time | Trip drop-off timestamp. |
| `passenger_count` | Whole number | Number of passengers recorded for the trip. |
| `trip_distance` | Decimal number | Trip distance in miles. |
| `PULocationID` | Whole number | Pickup location key. |
| `DOLocationID` | Whole number | Drop-off location key. |
| `fare_amount` | Decimal number | Base fare amount. |
| `Surge Fee` | Decimal number | Surge amount. |
| `Vehicle` | Text | Vehicle category. |
| `Payment_type` | Text | Recorded payment category. |

## Location Details

Source: `Dataset/Location Table.xlsx`  
Sheet: `Location Table`  
Rows: 265

| Column | Source type | Meaning |
|---|---|---|
| `LocationID` | Whole number | Location key used by `PULocationID` and `DOLocationID`. |
| `Location` | Text | Pickup or drop-off location name. |
| `City` | Text | City or area label used by the report slicer. |

## Report KPI Definitions

| KPI | Definition |
|---|---|
| Total Bookings | Count of trip records. |
| Total Booking Value | Sum of `fare_amount` plus `Surge Fee`. |
| Average Booking Value | Total booking value divided by trip count. |
| Total Trip Distance | Sum of `trip_distance`. |
| Average Trip Distance | Average of `trip_distance`. |
| Average Trip Time | Average difference between `Drop Off Time` and `Pickup Time`, expressed in minutes. |

## Verified Full-Dataset Totals

| Metric | Value |
|---|---:|
| Trip records | 103,728 |
| Booking value | $1,553,672.81 |
| Trip distance | 348,933.81 miles |
| Average trip time | 15.86 minutes |

## Data-Quality Notes

- All trip records have values in the supplied source columns.
- Trip IDs are unique in the supplied trip workbook.
- Pickup and drop-off location keys match the location workbook.
- Two trips have zero duration.
- Two trips exceed 100 miles.
- Some location names occur under more than one location ID.
- City labels include both `Bronx` and `The Bronx`.
- Some location records have `N/A` city values.

The report retains these records. They should be reviewed before using the dashboard for operational decisions.

## Interpretation Boundary

This is an analysis of the supplied June 2024 dataset. It is not a claim about Uber's complete business operations or current performance. Dataset provenance and redistribution permission were not included in the project package; verify those terms before public distribution.
