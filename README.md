# Transform new ACS table downloads from data.census.gov to FactFinder-like

Modify ACS tables downloaded form data.census.gov to look like the downloads from FactFinder for backwards compatibility of CTData's R ACS update scripts. **Key differences in file formats:**

* FactFinder downloads have a second column with a shorter FIPS code
* FactFinder column names are not variable names, but "row" names (eg HD01_VD01 instead of B01001_001E). We don't care about that, as the R scripts use column order, not column names.
* FactFinder second-row column names. Again, we don't care about that, as the R scripts use column order, not column names.

***This script does not change column names for variables, as guessing where to put ";" and "-" and ":" instead of "!!" is too messy***.

### How to use

1. Put newly downloaded .csv tables into `data.census.gov/` folder
1. Run the script
1. The result files will be saved to `factfinder/` folder, renamed to match FactFinder file names
