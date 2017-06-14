# Information Visualisation - D3.js Project

In this group project you will use D3.js to visualize a complex dataset. Below you
will find multiple datasets that you can use for the project. In addition to the datasets that we provide, we encourage you to combine them with other sources of data to create more insightful and information rich visualizations. Some points that will help to get you started:

1. Discuss with the group which you would like to use for the project. Once you have made a decision, let the teaching assistant know of your choice. *Note that at most two groups can use the same dataset. First come, first serve.*

2. Remember that you can find the course schedule on Blackboard (slides from the first practical session and course information). This week you will explore the datasets, think about what you want to do with the data, look for additional data sources, create a plan with the group and start working on the code. Next week you will hand in your mid-term report and give a presentation for all students in the group to receive feedback that will help you in improving the final result. For the presentation next week we expect you to have some preliminary visualizations to show. The presentations should be at most **7 minutes** long with additional **3 minutes** available for the questions. The mid-term report and slides should be uploaded to Blackboard. Please make sure to bring a USB stick with the slides on the day of the presentation, including a backup as PDF in case Powerpoint is not working properly (*e.g.* transitions, images or fonts).

3. The [D3.js example gallery ](https://github.com/d3/d3/wiki/Gallery) might serve as inspiration for what is possible in D3. Of course, you are free to use other sources of inspiration as well. Remember that D3.js and JavaScript are excellent for creating interactive visualizations. If you feel that you need more basic D3.js knowledge, have a look at the Dashing D3.js tutorial posted on Blackboard.

# Datasets

### 1. Climate Change: Earth Surface Temperature Data
Some say climate change is the biggest threat of our age while others say it’s a myth based on dodgy science. We are turning some of the data over to you so you can form your own view.

Even more than with other data sets that Kaggle has featured, there’s a huge amount of data cleaning and preparation that goes into putting together a long-time study of climate trends. Early data was collected by technicians using mercury thermometers, where any variation in the visit time impacted measurements. In the 1940s, the construction of airports caused many weather stations to be moved. In the 1980s, there was a move to electronic thermometers that are said to have a cooling bias.

Given this complexity, there are a range of organizations that collate climate trends data. The three most cited land and ocean temperature data sets are NOAA’s MLOST, NASA’s GISTEMP and the UK’s HadCrut.

We have repackaged the data from a newer compilation put together by the Berkeley Earth, which is affiliated with Lawrence Berkeley National Laboratory. The Berkeley Earth Surface Temperature Study combines 1.6 billion temperature reports from 16 pre-existing archives. It is nicely packaged and allows for slicing into interesting subsets (for example by country). They publish the source data and the code for the transformations they applied. They also use methods that allow weather observations from shorter time series to be included, meaning fewer observations need to be thrown away.

- **Data and Description Source**: Kaggle
- **Data Format**: Multiple CSV files (as .zip file)
- **External URL**: [Browse](https://www.kaggle.com/berkeleyearth/climate-change-earth-surface-temperature-data), [Download](https://drive.google.com/uc?id=0B9LmEAcBQRYIRXZsREtjZUZzRVE&export=download), or [Download](https://www.kaggle.com/berkeleyearth/climate-change-earth-surface-temperature-data/downloads/climate-change-earth-surface-temperature-data.zip)

### 2. Global Terrorism Database (GTD)

The Global Terrorism Database (GTD) is an open-source database including information on terrorist attacks around the world from 1970 through 2015 (with annual updates planned for the future). The GTD includes systematic data on domestic as well as international terrorist incidents that have occurred during this time period and now includes more than 150,000 cases. The database is maintained by researchers at the National Consortium for the Study of Terrorism and Responses to Terrorism (START), headquartered at the University of Maryland.

- **Data and Description Source:** Kaggle
- **Data Format:** One CSV file (as .zip file)
- **External URL:** [Browse](https://www.kaggle.com/START-UMD/gtd), [Download](https://drive.google.com/uc?id=0B9LmEAcBQRYIcFd0YzFydW81TEk&export=download), or [Download](https://www.kaggle.com/START-UMD/gtd/downloads/gtd.zip)

### 3. World University Rankings
Ranking universities is a difficult, political, and controversial practice. There are hundreds of different national and international university ranking systems, many of which disagree with each other. This dataset contains three global university rankings from very different places.

The Times Higher Education World University Ranking is widely regarded as one of the most influential and widely observed university measures. Founded in the United Kingdom in 2010, it has been criticized for its commercialization and for undermining non-English-instructing institutions.

The Academic Ranking of World Universities, also known as the Shanghai Ranking, is an equally influential ranking. It was founded in China in 2003 and has been criticized for focusing on raw research power and for undermining humanities and quality of instruction.

The Center for World University Rankings, is a less well know listing that comes from Saudi Arabia, it was founded in 2012.

- **Data and Description Source**: Kaggle
- **Data Format:** Multiple CSV files (as .zip file)
- **External URL:** [Browse](https://www.kaggle.com/mylesoneill/world-university-rankings), [Download](https://drive.google.com/uc?id=0B9LmEAcBQRYIUzRPMjZFVGRBbWs&export=download), or [Download](https://www.kaggle.com/mylesoneill/world-university-rankings/downloads/world-university-rankings.zip)

### 4. Flight Delays

The U.S. Department of Transportation's (DOT) Bureau of Transportation Statistics tracks the on-time performance of domestic flights operated by large air carriers. Summary information on the number of on-time, delayed, canceled, and diverted flights is published in DOT's monthly Air Travel Consumer Report and in this dataset of 2015 flight delays and cancellations.

- **Data and Description Source:** Kaggle
- **Data Format:** Multiple CSV files (as .zip file)
- **External URL:** [Browse](https://www.kaggle.com/usdot/flight-delays), [Download](https://drive.google.com/uc?id=0B9LmEAcBQRYIbkVmTnZQc0g5Ulk&export=download), or [Download](https://www.kaggle.com/usdot/flight-delays/downloads/flight-delays.zip)

### 5. House Price Index in the Netherlands
Prices of owner-occupied houses (excluding new constructions) were on average 7.4 percent higher in April 2017 than in April last year. This is the most substantial price increase since April 2002. Residential property prices have risen since June 2013, according to the price index of owner-occupied houses, a joint publication by Statistics Netherlands (CBS) and the Land Registry Office.

This dataset is about the change in house prices by region in the Netherlands, in the last 7 years, from Q1-2010 to Q1-2017. The change in prices are reported quarelty and anually.

- **Data and Description Source:** Centraal Bureau voor Statistiek (CBS)
- **Data Format:** One CSV file
- **External URL:** [Browse](http://statline.cbs.nl/StatWeb/publication/?DM=SLEN&PA=81885ENG&D1=0-5&D2=0,5-16&D3=79-l&LA=EN&HDR=T&STB=G1,G2&VW=T), [Download](https://raw.githubusercontent.com/kgavrilyuk/UvA-InfoVis-2017-Students/master/datasets/5.%20House%20Price%20Index/House_Price_Index.csv)

### 6. Amsterdam Demographics - Basisbestand Gebieden Amsterdam (BBGA)

Het Basisbestand Gebieden Amsterdam (BBGA) bevat kerncijfers op het niveau van de meest gebruikte gebiedsindelingen in Amsterdam: stadsdelen, de 22 gebieden van het gebiedsgericht werken, wijken, buurten, winkel- en werkgebieden en twee alternatieve buurtindelingen van de stadsdelen.

Het BBGA bevat meer dan 500 variabelen ingedeeld naar de volgende thema's: bevolking, leeftijd, wonen, openbare ruimte, verkeer, leefbaarheid, veiligheid, bedrijvigheid, sport en recreatie, welzijn en zorg, onderwijs, inkomen, participatie.

- **Data and Description Source**: Amsterdam Open Data
- **Data Format**: Two CSV files (as .zip file)
- **External URL**: [Browse](https://data.amsterdam.nl/index.html#?dte=https:%2F%2Fapi.datapunt.amsterdam.nl%2Fcatalogus%2Fapi%2F3%2Faction%2Fpackage_show%3Fid%3Db51154d8-2eca-4dd9-932d-63bca9ef0bf2&dtfs=T&mpb=topografie&mpz=9&mpv=52.3719:4.9012), [Download](https://github.com/kgavrilyuk/UvA-InfoVis-2017-Students/blob/master/datasets/6.%20Amsterdam%20Demographics/bbga.zip?raw=true)

### 7. Energielabels in Amsterdam

Dataset Energielabels in Amsterdam bevat ruwe data van afgegeven energielabels van gebouwen in Amsterdam. Per energielabel is de beschikbare informatie: gebouwinformatie dit betreft de postcode, het huisnummer, eventuele huisnummertoevoeging en een vrij veld dat gebruikt kan worden voor extra gebouw identificatie met verder het woningtype of hoofdgebruiksfunctie het certificaatnummer, de datum van opname en registratie door de adviseur, de labelwaarde (energie-index) en de labelklasse, bron van de opname het berekende gebouwgebonden energieverbruik in MJ, en indien beschikbaar m3 gas, kWh elektrisch, MJ warmte en het aantal m2 van het gebouw.

- **Data and Description Source**: Amsterdam Open Data
- **Data Format**: One CSV file
- **External URL**: [Browse](https://data.amsterdam.nl/index.html#?dte=https:%2F%2Fapi.datapunt.amsterdam.nl%2Fcatalogus%2Fapi%2F3%2Faction%2Fpackage_show%3Fid%3D4aa86565-e9b8-4a4f-a008-40896bf7f213&dtfs=T&mpb=topografie&mpz=9&mpv=52.3719:4.9012), [Download](https://github.com/kgavrilyuk/UvA-InfoVis-2017-Students/blob/master/datasets/7.%20Energielabels%20in%20Amsterdam/selectie%20gemeentes%20Amsterdam%204-1-2012.zip?raw=true), or [Download](http://open.datapunt.amsterdam.nl/uploads/energielabels-in-amsterdam/selectie%20gemeentes%20Amsterdam%204-1-2012.csv)

# Tips and Recommendations

### Use of other resources
If you feel that you need other resources, you can use the websites from which the data originates. For example, if you think that the GDP depends on population, you may need the
data on population of each country. Additionally, you can use other sources, such as [Google
Trends](https://www.google.com/trends/) to get regional data related to what people search for in The Netherlands and Europe. We encourage students to explore and combine other data as creativity and information rich visualization will positively contribute towards your final grade.

### Mix and Match

You are free to take different quantities from these datasets in order to investigate their correlation. For example, is the GDP growth of European countries related to unemployment?

### Python is your friend

While D3.js is great for building visually appealing and interactive figures, sometimes it can be hard to read the datasets in a convenient way. If you are more familiar with Python, you could inspect, prepare and pre-process the data using `NumPy`, `Pandas` or `SciPy`. The code snippet below could help to get you started reading a processing a TSV file (*tab seperated value*).

__Read a `.tsv` file in Python__
```python
import csv
with open("source_file.tsv") as tsvfile:
    tsvreader = csv.reader(tsvfile, delimiter="\t")
    for line in tsvreader:
        print(line)
        ''' Do some preprocessing such as:
            - handle missing data
            - correct the data
            - etc.
        '''
```

For reading big files (.csv) in Python you could use `Panda` library. It makes things a lot easier and faster. Also, this library is very helpful in getting rows and columns of your data based on conditions.

__Read a large `.csv` file in Python using Pandas__
```Python
import pandas as pd

# relative path of the data file
data_path = './data/flights.csv'

# read .csv file with panda
data = pd.read_csv(data_path)

# for debugging purposes, only consider the first 100 rows
# if your data is really large (100s of thousands of rows)
rows = data.head(100)

# index all the rows, and only the 8th column (zero-based indexing)
column_seven = rows.ix[:, 7]

# now, get the values in that column
values = column_seven.values
```

For reading Excel spreadsheet files (.xls)  in Python you could use the `xlrd` package which can be downloaded from [pypi.python.org](https://pypi.python.org/pypi/xlrd). After reading and processing the data, the `json` package can be used for exporting the data to JSON file which is suitable for reading in D3.js. Make sure to look at the original dataset table, to be sure that you are loading data correctly.

__Write to a `.json` file in Python__
```python
import json
with open("target_file.json", "w") as outfile:
    json.dump(data, outfile)
```

# Other Data Sources

1. EU Open Data [Link](http://open-data.europa.eu/en/data/)
2. Rijksoverheid Data [Link](https://data.overheid.nl/)
3. Amsterdam Open Data [Link](http://data.amsterdam.nl/)
4. NYC Open Data [Link](https://data.cityofnewyork.us/)
5. Kaggle Datasets [Link](https://www.kaggle.com/datasets)
6. Centraal Bureau voor Statistiek (CBS) [Link](https://www.cbs.nl/en-gb)

# Get Inspired

1. Bloomberg best visualizations [Link](https://www.bloomberg.com/graphics/infographics/)
2. Fifteen mind-blowing data visualizations [Link](http://blog.udacity.com/2015/01/15-data-visualizations-will-blow-mind.html)
3. A tour through the visualization zoo [Link](http://delivery.acm.org/10.1145/1750000/1743567/p59-heer.pdf?ip=145.18.164.25&id=1743567&acc=OPEN&key=0C390721DC3021FF%2E86041C471C98F6DA%2E4D4702B0C3E38B35%2E6D218144511F3437&CFID=948339258&CFTOKEN=99167172&__acm__=1497444155_4164f282b5ff59d5dad7e4bf2e0a48bc)
4. The eyes have it: a task by data type taxonomy for information visualizations [Link](https://www.cs.umd.edu/~ben/papers/Shneiderman1996eyes.pdf)
