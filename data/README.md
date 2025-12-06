# World Bank Economic Indicators Dataset

## Overview

This project uses economic indicators data from the **World Bank's World Development Indicators (WDI)** database.

## Download Instructions

### Website

Visit: https://wdi.worldbank.org/table

### Datasets Required

The following specific economic indicator datasets are needed for this project:

1. **WV.1 - Size of the economy**

   - File: `WV.1_Size_of_the_economy.xls`
   - Contains: GDP and economic size indicators

2. **4.1 - Growth of Gross Domestic Product**

   - File: `4.1_Growth_of_Gross_Domestic_Product.xls`
   - Contains: GDP growth rates

3. **4.2 - Structure of value added**

   - File: `4.2_Structure_of_value_added.xls`
   - Contains: Value added by sector

4. **4.3 - Structure of manufacturing**

   - File: `4.3_Structure_of_manufacturing.xls`
   - Contains: Manufacturing sector composition

5. **4.4 - Structure of merchandise exports**

   - File: `4.4_Structure_of_merchandise_exports.xls`
   - Contains: Export structure data

6. **2.5 - Unemployment**

   - File: `2.5_Unemployment.xls`
   - Contains: Unemployment rates

7. **1.2 - Poverty rates at international poverty lines**

   - File: `1.2_Poverty_rates_at_international_poverty_lines.xls`
   - Contains: Poverty rates (Part 1)

8. **1.2.2 - Poverty rates at international poverty lines (Part 2)**
   - File: `1.2.2_Poverty_rates_at_international_poverty_lines_Part_2.xls`
   - Contains: Poverty rates (Part 2)

### How to Download

1. Go to https://wdi.worldbank.org/table
2. Search for each table number (e.g., "WV.1", "4.1", "4.2", etc.)
3. Click on the table to open it
4. Click "Download" button (usually in the top-right corner)
5. Select Excel format (.xls or .xlsx)
6. Save the files to the `row/` folder in this directory

### Folder Structure

```
data/
├── row/                          # Raw data files (gitignored)
│   ├── WV.1_Size_of_the_economy.xls
│   ├── 4.1_Growth_of_Gross_Domestic_Product.xls
│   ├── 4.2_Structure_of_value_added.xls
│   ├── 4.3_Structure_of_manufacturing.xls
│   ├── 4.4_Structure_of_merchandise_exports.xls
│   ├── 2.5_Unemployment.xls
│   ├── 1.2_Poverty_rates_at_international_poverty_lines.xls
│   └── 1.2.2_Poverty_rates_at_international_poverty_lines_Part_2.xls
│
├── preprocessed/                 # Processed datasets (gitignored)
│   └── economic_indicators_dataset.csv
│
└── README.md                      # This file
```

## Notes

- Raw data files (`.xls`, `.xlsx`, `.csv`) are gitignored to keep the repository size small
- Only the processed datasets are created locally when running the notebooks
- All datasets are public and freely available from the World Bank
- Ensure you download data for **all countries** to include Algeria in the analysis

## Processing

After downloading the datasets to the `row/` folder, run the notebook:

```
notebooks/economic_indicators_dataset.ipynb
```

This will:

- Load all raw datasets
- Clean and standardize the data
- Merge all indicators into a single comprehensive dataset
- Save the processed data to `preprocessed/economic_indicators_dataset.csv`

## Data References

- **Source**: World Bank - World Development Indicators (WDI)
- **URL**: https://wdi.worldbank.org/
- **License**: Creative Commons Attribution 4.0 International License (CC BY 4.0)
