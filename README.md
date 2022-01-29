# bikesharing

Analyzing Citibike bike-sharing data with Tableau.

## Overview of Project

The city of Des Moines has requested an analysis of data from New York Citibike.  They're thinking of implementing a similar system in Des Moines, and will use conclusions from the analysis to refine their supporting business strategy.  We will look specifically at data regarding user ride times (both checkout/turn-in times and ride durations), and also analyze that data further by gender demographic.

## Link to Tableau Story:

[Click here to view the interactive Tableau Story]

---

## Deliverable 1: Clean the Data

In order for us to properly utilize and visualize the "Trip Duration" data, it must be converted from its raw interger format to a date-time format.  This is accomplished by reading the source .csv file into a pandas dataframe (in Jupyter Notebook) and converting the column with the to_datetime() method.

![dtypes_unclean.png]()

![dtypes_clean.png]()

Once the correct data-types have been verified, the dataframe is then exported to a new .csv file ("data.csv").

![exported_csv.png]()

---

## Deliverable 2: Create Visualizations for the Trip Analysis

![trip_duration_all_users.png]()

![trip_duration_by_gender.png]()

![heatmap_all_users.png]()

![heatmap_by_gender.png]()

![usertype_gender_use_breakdown.png]()

---

## Deliverable 3: Create Tableau Story to combine visualizations

