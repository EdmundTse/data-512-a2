# DATA512 A2: Bias in data

Wikipedia is a free and openly editable online encyclopedia. Despite its nature of open collaboration, [critics note](https://en.wikipedia.org/wiki/Criticism_of_Wikipedia) that there is bias in its coverage.

In this notebook, we examine bias in English Wikipedia's coverage of politicians and the quality of these articles.

## Data sources

For Wikipedia data about politicians, we use data processed by Os Keyes from [Politicians by Country from the English-language Wikipedia](https://figshare.com/articles/Untitled_Item/5513449), which is available as a Fileset on figshare under the CC-BY-SA 4.0 license. The file named `page_data.csv` was extracted from the Fileset and saved to the `data_raw` folder.

Format: {page, country, rev_id}

Population data is from the 2018 World Population Data Sheet Population Reference Bureau's [World Population Data Sheet](http://www.worldpopdata.org/table), using the "Population mid-2018 (millions)" indicator with geography filter set to regions Africa, Asia, Europe, Latin America And The Carribean, Northern America and Oceania, plus all countries selected. Instead of using the PRB website directly, we used cached copy of WPDS 2018 CSV file hosted at [this Dropbox location](https://www.dropbox.com/s/5u7sy1xt7g0oi2c/WPDS_2018_data.csv?dl=0), which we saved to the `data_raw` folder. The license for this dataset is unknown.

Format: {geography, population in millions}

To measure quality, we will use Wikimedia's web service called [Objective Revision Evaluation Service (ORES)](https://ores.wikimedia.org/) to make predictions about articles' quality rating according to the English Wikipedia 1.0 (wp10) assessment scale.

## How to run the code

The code is supplied in a Python 3 Jupyter notebook, named: `hcds-a2-bias.ipynb` in this folder. Open this folder in a Python 3 Jupyter notebook environment, load the notebook then Run All Cells.

If the raw data JSON file `ores_responses.json` containing the ORES API responses are present in the `data_raw` folder, the local copy will be used. Otherwise, the Wikimedia APIs will be called to download data from the source.

Cleaned data is output into the `data_clean` folder as `combined.csv`.

The results of this analysis, in the form of tables of reuslts, saved into the `results` folder as CSV files.