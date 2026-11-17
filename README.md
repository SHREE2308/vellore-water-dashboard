# Vellore Water Security Command Center

A single-page Power BI executive dashboard for water resource planning in Vellore district, Tamil Nadu. Covers 5 assembly constituencies from 2013–2025.

## Key Features
- Unified executive view with KPIs: Water Available, Water Demand, Water Gap, Gap %, Supply Coverage %, GW Extraction Stage %
- Demand-supply balance, constituency comparisons, rainfall seasonality, and gap analysis
- Dark water-themed design (1920x1080, 16:9)

## Files
| Path | Purpose |
|---|---|
| `Vellore_Water_Security_Command_Center.pbix` | Main dashboard (self-contained, data embedded) |
| `vellore_measures.dax` | All 49 DAX measures, exported from the PBIX model |
| `data/*.csv` | Source extracts (9 files) |
| `flat_dashboard.csv` | Flat denormalised export for portability |
| `vellore_data.zip` | Packaged copy of the source data |

## Data
9 CSV datasets covering constituency, year, rainfall (monthly/observed), groundwater (CGWB), water bodies, status guide, and source references.

The PBIX imports the CSVs from `E:\Vellore_Water_Security_Command_Center\data\` (absolute path). Data is already embedded, so the report opens and renders without a refresh. If you clone the repo to a different folder or drive, update the data source path (Home > Transform data) before clicking Refresh.

## Usage
1. Open `Vellore_Water_Security_Command_Center.pbix` in **Power BI Desktop**.
2. Use the **Year** and **Constituency** dropdown slicers to filter the page.
   - Both slicers start on **All**.
   - They are multi-select: after clearing "Select all", pick one or more values; click "Select all" to return to All.
3. **Refresh** re-imports the CSVs from `data/`.
4. The **Water Available vs Demand** chart is a clustered column chart with value labels, so any slicer selection — including a single year — displays exact Available and Demand values (a single year cannot form a line segment on its own).

## Notes
- 13 years (2013–2025) × 5 constituencies = 65 fact rows. 2017 is included.
- Rainfall metrics are monthly; the monthly rain measure and `Rainfall Monthly` table are linked to both Year and Constituency.
