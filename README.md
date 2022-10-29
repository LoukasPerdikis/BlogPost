# Seattle AirBNB Analysis

## Motivation
This experiment served to investigate particular questions surrounding AirBNB using company data for the city of Seattle, WA. The experiment was conducted using the CRISP-DM data science approach:

1. Business understanding
2. Data understanding
3. Data preparation
4. Modeling
5. Evaluation and Scoring
6. Communication

Comprehensive discussion and details on each of these sections can be found in ipynb notebook found in this repository, but a summary will be provided here.

## Business understanding
The AirBNB business serves to connect hosts and guests, where guests can rent living spaces from hosts for a time. The hosts are responsible for all things property related, while the guests can use the living space as needed for the duration of their stay.

## Data understanding
Three csv files were used to analyse the Seattle AirBNB data:

1. calendar.csv - deals with listing availability and pricing
2. listings.csv - deals with comprehensive details for each listing
3. reviews.csv - deals with guest reviews after having stayed at listed properties

Using the above datasets alongside the established business understanding, three questions were asked which would form the basis of the analysis

**A) How does the time of year affect property availability?**

**B) What is the most common type of property rented?**

**C) Can the listing review score be predicted?**

Each of these questions were answered using basic analysis alongside supervised machine learning where necessary.

## Data preparation
The libraries used in this analysis were basic libraries commonly associated with data science analysis:

1. Numpy
2. Pandas
3. Matplotlib.pyplot for plotting
4. Various libraries from sklearn
5. Seabron for asthetic purposes
6. Warnings for notebook neatness

The csv files provided were mostly ready for use, where the only cleaning necessary was in the treatment of nulls and formatting in terms of price (the column was of the format "$X" and hence would be interpreted as a string instead of a numeric value).

## Modeling
The only modeling required was for the third question (please refer below) and included use of a linear regression model from the sklearn library.

## Evaluation and Scoring
Answeres to each of the questions are summarised here. The first two questions did not require machine learning but rather graphical analysis of the data.

**Question 1: How does the time of year affect property availability?**
This question was answered by plotting the number of available and unavailable listings on a monthly basis throughout the year. It was found that there was an icnrease of unavailable listings during the summer months, which suggests seasonal influence during the holiday periods. The same was true for the festive period between Christmas and New Year's Day.

**Question 2: What is the most common type of property rented?**
This questions simply required a categorical value count across all property types that had been rented. While there were more house type listings than apartment type (they were very similar in total number), it was found that most of the rented listings were of apartment type.

**Question 3: Can the listing review score be predicted?**
The short answer to this question is simple: no.
The chosen features did not seem to encapsulate the logic behind the received rating of rented listings, with r2 scores on training and testing data at a measly 0.108 and 0.109 respectively. Alternatively, it could be the case that review scores are simply too subjective and anecdotal to be effectively modeled. 

Features were chosen according to host interactions, property characteristics, and guest convenience. The features containing null values included host response rate, number of bathrooms, and number of bedrooms. Nulls for the host response rate were interpreted as hosts simply not responding, and hence the null values were included in the analysis. For both the number of bathrooms and bedrooms, nulls were interpreted as the property having 0, and hence these nulls were filled with 0s.

A better experiment to have asked may have been to predict listing price instead of review score rating.

## Communication
Occurs within this README.md file, the actual python notebook, and a blog on Medium, accessible here: https://medium.com/@loukas.perdikis/analysing-seattle-airbnb-data-humble-beginnings-8c0afe1c6fd0

## Acknowledgements
Udacity course material - providing much of the information required to effectively conduct this study.
