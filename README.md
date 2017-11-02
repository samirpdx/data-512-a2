# data-512-a2

## A2. Bias in Data

### Goal of the Project:

The goal of this project is to explore bias through data obtained from Wikipedia articles on political figures from various countries.

First, a data set of Wikipedia articles will be combined with a second data set of country populations. A machine learning tool called ORES will be used on this combined dataset to estimate the article quality.

Next, an analysis will then look at coverage of politicians on Wikipedia and the how quality of articles about politicans varies between countries.

Then visualizations will be created as follows:

1. The countries with the greatest and least coverage of politicians on Wikipedia compared to their population.

2. The countries with the highest and lowest proportion of high quality articles about politicians.

Finally, I will summarize how this assignment affected my understanding of causes and consequences of bias on Wikipedia.


### License of the Source Data

Wikipedia article data for "Politicians by country from the English-language Wikipedia"

To obtain this data, I used the following link to download the zipped data file:

[Politicians by Country from the English-language Wikipedia](https://figshare.com/articles/Untitled_Item/5513449)

To obtain this data, I used the following link to download the data file:

    Data publicly shared on FigShare by Oliver Keyes, HCDE 512 TA/Instructor.  Released under the CC-BY-SA 4.0 license.
    

Population (Mid-2015) by country data was made available by the PRB (Population Reference Bureau)

[Population Mid-2015 Data](http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14)

Article Quality Prediction Data was gathered from the Wikimedia ORES API, Wikimedia Foundation, 2017. 

    Released under the CC-BY-SA 4.0 license.

<a href = "https://wikimediafoundation.org/wiki/Terms_of_Use/en"> WikiMedia Terms of Use</a>


### Links to Relevant API Documentation for ORES

ORES (Objective Revision Evaluation Service) is a machine learning web service and API provided by WikiMedia that can estimate Wikipedia article quality.

[documentation](https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores_context_revid_model)

[endpoint](https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores_context)

This data is made available via CC0 1.0 license.


### Data set fields (final CSV output)

Below are the columns in order found in the 'final_merged.csv' file:

column name | value
--- | ---
article_name | string
country | 
revision_id | int
article_quality | string
population | string



### Special considerations and Known Issues

- The API call for ORES prediction scores is sped up with several rev_id input values as opposed to one at a time. 
  This can be done by creating one long string of rev_id values with a delimiter in between.
- There will be some rev_id values without any associated prediction scores.  To handle these and prevent errors 
when making calls to ORES, a suggestion is to insert a try/except statement.
- The entire call (done in 100 rev_id chunks) will take about roughly 3 minutes.  It is recommended to use the Python
"pickle" package in order to avoid having to re-run the call.
- 


Directory Structure
---------------------
```
data-512-a1/

  |- final_data/
     |- final_merged.csv
  |- images/
     |- articles_per_pop_bot10.png
     |- articles_per_pop_top10.png
     |- hqa_country_bot10.png
     |- hqa_country_top10.png
  |- imported_data/
     |- page_data.csv
     |- Population Mid-2015.csv
  |- LICENSE     
  |- README.md
  |- hcds-a2-bias-in-data.ipynb
```

### Reproducibility Steps

Please reference the Jupyter Notebook,'hcds-a2-bias-in-data.ipynb', to see step by step instructions of how to perform the analysis.

NOTE: The follow these steps, a user will need to be familiar with the Python programming language.

Steps are broken out as follows:

    Step 1: Getting Data Sets 
    
    Step 2: Getting Article Quality Predictions using ORES
    
    Step 3: Combining the Data Sets
    
    Step 4: Analysis

    Step 5: Visualization
    
    Step 6: Reflections

### Attributions

Jonathan Morgan (Professor, DATA 512, Human Centered Data Science, University of Washington) and
Oliver Keyes (TA, DATA 512, Human Centered Data Science)for example source code provided for API data requests.
    - Specific attributes found in 'hcds-a2-bias-in-data.ipynb'

Additional instructions provided by [HCDS Fall 2017 - Course Wiki](https://wiki.communitydata.cc/HCDS_(Fall_2017)/Assignments#Weekly_reading_reflections).  CC-BY-SA 3.0