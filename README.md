# python-api-challenge

Glantz Adam Bootcamp RUT-VIRT-DATA-PT-04-2023-U-LOLC-MWTH - Module 6 Python API Challenge

Python API Challenge

**TABLE OF CONTENTS**
1. Project Description
2. Installation
3. Contributing
4. Acknowledgements


**1-PROJECT DESCRIPTION**

In this assignment, we were tasked with using Python requests, APIs, and JSON dictionaries to answer questions about the relationship between certain meterological variables and latitude (WeatherPy), as well as to determine the best places for a vacation given the author's climate preferences.

**For WeatherPy:** Dependencies were installed. For a particular day, random combinations of latitude and logitude were generated at set intervals, and then cities close to those coordinates were identified in the citipy dataset and printed. Each city was matched against the data in https://api.openweathermap.org/data/2.5/weather and sequentially printed as meteorlogical data for them was captured in a list, with unmatched cities excluded. After verification of the volume and variables of the list, scatter plots were created from the city data of latitude vs. maximum temperature, humidity, cloudiness, and wind speed. The data was divided into northern hemisphere and southern hemisphere subsets by latitude ranges, and the operation was confirmed by printing out samples. Scatter plots using the same variables as before were created from the data in each hemisphere, this time with a regression model and line added and Pearson's r calculated for each plot. Analysis for each set of scatterplots' linear relationships was provided. 

**RESULT: The fact that temperature increases as one travels closer to the equator and decreases as one moves further away from it was established with empirical data. None of the other variables had a significant relationship with latitude.**

It must be stated at the outset that the generalizability of the WeatherPy findings across all plots is limited because the plots represent a single day, 5/19/2023. Since the weather fluctuates in any locale, this day may exhibit atypical meteorological patterns in many places and thus not convey more enduring weather features. Analyzing data over time would address this small-n problem.

Moreover, relying on the citipy dataset overrepresents regions that have more major cities and correspondingly underrepresents those with fewer large cities or fewer cities in general. The longitude and latitude range covers the entire earth, but there is an urban bias that might be partially mitigated by weighting regions by the number and size of their cities.

**For VacationPy:** City data from citipy was plotted on a map of the world. Cities characterized by the author's ideal weather conditions were isolated and displayed in tabular form. Hotels within a set proximity to each city were pulled in from https://api.geoapify.com/v2/places, with the list of city by hotel (or of failures to match cities with hotels) noted - as instructed, the results were capped at approximately 10 hotels to limit excess API calls. The author's ideal cities were then plotted on another map.

-- OBSERVATIONS FROM THE ANALYSIS ARE ALSO PROVIDED IN THE WEATHERPY FILE OF THE JUPYTER NOTEBOOK FILE


**2-INSTALLATION**

This project is coded in Python 3.10.9
The project files have an .ipynb extension, so they are meant to be viewed in Jupyter Notebook.

*Project files -*
    WeatherPy,
    VacationPy
    
*Data file in output_file subfolder =*
    cities.csv,
    *10 printouts of scatterplots as requested in the instructions*

*Dependencies -*

WeatherPy:
    matplotlib.pyplot,
    pandas,
    numpy,
    requests,
    time,
    scipy.stats, including linregress,
    json

VacationPy:
    hvplot.pandas
    pandas
    requests

*Resources -*
    cities.csv (from citipy, for both projects),
    https://api.openweathermap.org/data/2.5/weather (for WeatherPy),
    https://api.geoapify.com/v2/place (for VacationPy)

**NOTES**

We were instructed to put WeatherPy and VacationPy in their own subdirectories, but I kept them at top level for ease of access.

I limited the output of hotels by city in the VacationPy code to approximately 10 (i.e., 15 to account for cities distant from hotels), as requested by the instructions.

This project assumes that the source .csv file listed above retains its original name and is in a folder labeled "output_data" that is one level below where the Python files reside. If you do not follow this relative placement, the programs will not run and the path will need to be updated.


**3-CONTRIBUTING**

Adam Glantz: adamglantz@yahoo.com


**4-ACKNOWLEDGEMENTS**

I shared code with two classmates, *Karishma Sanghvi* and *Nancy K. Sakyi*. I also consulted with three GitHub repos regarding very similar data visualization challenges I found through a Google Search:

    Author: Miles Lucey: San Jose, CA USA, Feb 2019 (mileslucey@gmail.com) = https://github.com/mileslucey/weatherpy/blob/master/WeatherPy.ipynb
    Author: Matt Debnar: New York, NY USA, June 2020 (https://debnar.com / @debnar) = https://github.com/bbixby/python-api-challenge/blob/master/WeatherPy/WeatherPy.ipynb
    Author: Khoi-Duong [sic]: Jan 2023 = https://github.com/Khoi-Duong/WeatherPy-VacationPy/blob/main/WeatherPy_VacationPy_FinalCode/VacationPy_Solved.ipynb