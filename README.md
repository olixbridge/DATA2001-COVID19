SA2 data: https://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/1270.0.55.001July%202016?OpenDocument#Data

# DATA2001-COVID19
This is a group project for USYD DATA2001. We are processing and analysing COVID19 data in Australia 2020.

Mainidea:
– Calculate a 'risk' or 'vulnerability score' per suburb in Greater Sydney wrt. viruses
• BasedonABSdataaboutpopulation and availability of health services
– Visualise and correlate with Covid-19 data


Goal: Practical experience with data variety, data analysis, and presentation – Technologies as covered in this course: Python, Jupyter notebooks, and SQL

– Three tasks:

1. Data import and integration
• Weprovidedcensusdata,COVID-19stats,anddataabouthealth-services
• Needstobecombined,eg.viaspatialjoin
• Feelfreetoextendwithowndatasets
• Milestone1:IntegrationofprovideddatasetstobereadyinWeek11tutes

2. Vulnerability Analysis
• Computationof'vulnerability'score;exampleformulagiven
• Whenaddingotherdatasets,feelfreetoadjustformula
• CorrelationofyourscorewithCOVID-19testsandconfirmedcases

3. Documentationand(brief)Report

The data we are using:
– ABS Data
– Census data on neighbourhoods (SA2-level areas) in Greater Sydney
such as population, land area, number of dwellings, gender and age distribution – Health Services in NSW
– Location and some states (e.g. average available hospital beds)
– COVID-19 Data
– Conductedtestsandconfirmedcasesbypostcodetocheckforcorrelationwith
– Note that SA2-level data from the ABS does not always match suburbs,
and that the health services have a GPS location, but not the neighbourhoods
– cf.tutorialthisweekonhowtoretrieveboundarydataforneighbourhoodstoo


----------------------------------------------------------------
Vulnerability Analysis

1. Dataset Description
What are your data sources and how did you obtain and pre-process the data?

StatisticalAreas.csv: area id, area name, parent area id
Neighbourhoods.csv: area id, area name, land area, population, dwellings, businesses, median income, av PopulationStats2016.csv:area id, area name, age distribution, total persons, females, males
HealthServices.csv: NSW Postcodes.csv
SA2: boundary data
Traffic_Volume_Viewer_-_2020_Data.geojson:

We pre-process the data and calculated the below attributes that influence the vulnerability score
population density=population divided by neighbourhood’s land area
population age=percentage of a neighbourhood’s population age 70+
healthservice density =number of health services per suburb per 1000 people 
hospitalbed density=number of hospital beds per suburb per 1000 people
traffic_density= number of traffic count per suburb per 1000 people

2. Database Description
Into which database schema did you integrate your data (preferable shown with a diagram)? Which index(es) did you create, and why?

3. Vulnerability Score Analysis
Show which formula you applied to compute the vulnerability score per neighbourhood, and give an overview of vulnerability results. This can be done either in text by highlighting some representative results, or with a graphical representation onto a map (preferred).

vulnerability = S(z(population density)+z(population age)−z(healthservice density)−z(hospitalbed density)+z(traffic_density))


4. Correlation Analysis
How well does your score correlate to the number of COVID-19 cases in the given suburbs? Is there any correlation with the number of COVID-19 tests in the neighbourhoods?








