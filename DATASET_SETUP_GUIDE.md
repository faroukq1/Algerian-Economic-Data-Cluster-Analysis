# Dataset Setup Guide

## Problem: Empty Dataset

If you're getting a dataset with only 1 row and 1 attribute (just the Country column), it means the data files are not being found or loaded.

## Solution

### Step 1: Verify Data Files Exist

The notebook expects data files in: `data/row/`

Required files:

- `WV.1_Size_of_the_economy.xls`
- `Population_Total.xls`
- `Population_Growth.xls`
- `Urban_Population.xls`
- `Labor_Force_Total.xls`
- `Labor_Participation_Rate.xls`
- `Education_Expenditure.xls`
- `Literacy_Rate.xls`
- `School_Enrollment.xls`
- `Energy_Consumption.xls`
- `Renewable_Energy.xls`
- `Natural_Resources_Rents.xls`
- `Forest_Area.xls`
- `Water_Resources.xls`
- `Infrastructure_Index.xls`
- `Internet_Users.xls`

### Step 2: Download the Files

1. Visit: https://wdi.worldbank.org/table
2. Search for each table (WV.1, 4.1, 4.2, etc.)
3. Download in Excel format
4. Save to `data/row/` folder

Refer to `data/README.md` for complete download instructions.

### Step 3: Run the Notebook Diagnostics

Cell 2 will show you which files are found and which are missing:

- ✅ = File found
- ❌ = File missing

### Step 4: Expected Output

Once all files are in place, you should see:

**Cell 2 Output:**

```
📂 CHECKING DATA FILES
============================================================
Data folder: ../data/row
Folder exists: True
   ✅ size_economy: WV.1_Size_of_the_economy.xls
   ✅ population: Population_Total.xls
   ... (all files found)

📊 Summary: 16 available, 0 missing
```

**Final Output (Cell 14):**

```
✅ FINAL DATASET REPORT
============================================================

🇩🇿 Algeria found in dataset!
   Country: Algeria
   Data points: 45 / 50

📊 Dataset Statistics:
   Total countries: 217
   Total indicators: 45
   Data completeness: 82.5%
```

## Troubleshooting

### Issue: "File not found" for all files

**Cause:** Data files haven't been downloaded yet

**Solution:**

1. Go to https://wdi.worldbank.org/table
2. Download all required datasets
3. Place in `data/row/` folder

### Issue: Only 1 country, single attribute

**Cause:** All data files are missing or can't be read

**Solution:**

1. Check that files are in `data/row/` folder
2. Verify file names match exactly (case-sensitive)
3. Ensure files are in Excel format (.xls or .xlsx)
4. Try re-downloading the files

### Issue: Algeria not found

**Cause:** Files loaded but Algeria name might be different

**Solution:**

1. Check Cell 2 output for available countries
2. Look for country names like "Algeria", "DZA", or similar
3. Verify data contains all countries (should have 200+ countries)

## Data Processing Steps

The notebook performs these steps in order:

1. **Cell 2:** Check which files exist
2. **Cells 3-4:** Load data loading function and Size of Economy
3. **Cells 5-9:** Load and combine:
   - Population data
   - Labor data
   - Education data
   - Environment data
   - Infrastructure data
4. **Cell 10:** Merge all datasets
5. **Cell 11:** Clean and validate
6. **Cell 12:** Create derived metrics
7. **Cell 13:** Save to CSV
8. **Cell 14:** Final report with Algeria check

## Expected File Sizes

Each downloaded file should be:

- Range: 50KB - 500KB typically
- Format: .xls or .xlsx
- Readable by pandas.read_excel()

## Output File

Once processing is complete:

- **Location:** `data/preprocessed/human_natural_capital_development_indicators.csv`
- **Size:** Typically 1-5MB depending on data availability
- **Format:** CSV with Country column + multiple indicator columns

## Need Help?

If you still have issues:

1. Run Cell 2 to see which files are available
2. Check the error messages in the output
3. Verify file paths match exactly: `../data/row/filename.xls`
4. Try downloading files manually from: https://wdi.worldbank.org/table
