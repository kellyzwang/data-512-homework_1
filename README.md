# data-512-homework_1

HW1: Professionalism & Reproducibility

### Project Goal

This repository construct, analyze, and publish a dataset of monthly article traffic for a select set of pages from English Wikipedia from July 1, 2015 through September 30, 2024.


### License

The source data for this dataset is licensed under:
- [Creative Commons Attribution-ShareAlike 3.0 (CC-BY-SA 3.0)](https://creativecommons.org/licenses/by-sa/3.0/deed.en)
- [GNU Free Documentation License (GFDL)](https://www.gnu.org/licenses/fdl-1.3.en.html)
- For more details, please refer to the [Wikimedia Foundation terms of use](https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use)

How the Terms of Use applies to the datasets:
Users of this datasets need to credit the original source and follow the license rules if you change or share it.

### API Documentation
- [Wikimedia REST API](https://www.mediawiki.org/wiki/Wikimedia_REST_API) was used for data acquisition.
- [Link to API documentation](https://wikimedia.org/api/rest_v1/#/Pageviews%20data)


### Final Output Filenames and Directory Structure

```
├── img
|   └── Maximum_Average_and_Minimum_Average.png
|   └── Top_10_Peak_Page_Views.png
|   └── Fewest_Months_of_Data.png
├── LICENSE
├── README.md
├── rare-disease_cleaned.AUG.2024.csv
├── rare-disease_monthly_cumulative_start201507-end202409.json
├── rare-disease_monthly_desktop_start201507-end202409.json
├── rare-disease_monthly_mobile_start201507-end202409.json
├── rare_disease_article_traffic_analysis.ipynb
```

### Description of Output Files

**img**: All images files of the analysis graphs generated from the notebook.

**rare-disease_monthly_mobile_start201507-end202409.json**: Monthly mobile access

**rare-disease_monthly_desktop_start201507-end202409.json**: Monthly desktop access

**rare-disease_monthly_cumulative_start201507-end202409.json**: Monthly cumulative data

### Data Description

**rare-disease_cleaned.AUG.2024.csv**: Source data file that contains a specified subset of Wikipedia article pages that represents a large number of articles related to rare diseases. This list of pages was collected by using a database of rare diseases maintained by the [National Organization for Rare Diseases (NORD)](https://rarediseases.org) and matching them to Wikipedia articles that are either about a rare disease or have a section that mentions a rare disease.

**rare-disease_monthly_desktop_start201507-end202409.json**: Time series of monthly activity of actual user pageview requests for monthly desktop data. Data is from 2015 July 1, 2015 through September 30, 2024.

**rare-disease_monthly_mobile_start201507-end202409.json**: Time series of monthly activity of actual user pageview requests for monthly mobile data. Data is from 2015 July 1, 2015 through September 30, 2024.

**rare-disease_monthly_cumulative_start201507-end202409.json**: Time series of monthly activity of actual user pageview requests for monthly cumulative data (both desktop and mobile access). Data is from 2015 July 1, 2015 through September 30, 2024.


All 3 datasets are saved as JSON files ordered using article titles as a key for the resulting time series data for that article. The ‘access’ field is removed for mobile and cumulative files as it is misleading.


### To Reproduce the Analysis

 The `rare_disease_article_traffic_analysis.ipynb` notebook contains code to collect data from the API and generate all JSON data files and images for visual analysis.

 The source file `rare-disease_cleaned.AUG.2024.csv` must be present in the repository.

 Proper parameter values must be set to map values into the `API_REQUEST_PER_ARTICLE_PARAMS`.




### Data Issues

- Not all articles have data available for all months. For example, the article "2006 in Africa" has data for 111 months, while the article "2009 Swine Flu Pandemic Vaccine" contains data for only 54 months.
