# bikesharing

Analyzing Citibike bike-sharing data with Tableau.

## Overview of Project

The city of Des Moines has requested an analysis of data from New York Citibike.  They're thinking of implementing a similar system in Des Moines, and will use conclusions from the analysis to refine their supporting business strategy.  We will look specifically at data regarding user ride times (both checkout/turn-in times and ride durations), and also analyze that data further by gender demographic.

## Link to Tableau Story:

[Click here to view the interactive Tableau Story](https://public.tableau.com/app/profile/matthew.a.hardy/viz/CitibikeChallenge_16434005025880/NYCCitibikeAnalysis?publish=yes)

---

## Deliverable 1: Clean the Data

In order for us to properly utilize and visualize the "Trip Duration" data, it must be converted from its raw interger format to a date-time format.  This is accomplished by reading the source .csv file into a pandas dataframe (in Jupyter Notebook) and converting the column with the to_datetime() method.
- Link to Jupyter Notebook file "NYC_CitiBike_Challenge.ipynb" can be found [HERE](https://github.com/ZeroDarkHardy/bikesharing/blob/main/NYC_CitiBike_Challenge.ipynb)

![dtypes_unclean.png](https://github.com/ZeroDarkHardy/bikesharing/blob/main/resources/dtypes_unclean.png)

![dtypes_clean.png](https://github.com/ZeroDarkHardy/bikesharing/blob/main/resources/dtypes_clean.png)

Once the correct data-types have been verified, the dataframe is then exported to a new .csv file ("data.csv").

![exported_csv.png](https://github.com/ZeroDarkHardy/bikesharing/blob/main/resources/exported_csv.png)

---

## Deliverable 2: Create Visualizations for the Trip Analysis

### Trip Durations per User

![trip_duration_all_users.png](https://github.com/ZeroDarkHardy/bikesharing/blob/main/resources/trip_duration_all_users.png)

- Our first chart tracks the average trip duration per number of users.  We can see that the vast majority of users check out the bikes for less than 20 minutes, reaching peak usage around just 5 minutes per user.
- Five minutes doesn't seem like a very long time to check out a bike, and might be worth investigating if that's purely because the users don't need to cover a large distance, or if the bikes themselves are unpleasant to use, somehow.

### Trip Durations per User (By Gender)

![trip_duration_by_gender.png](https://github.com/ZeroDarkHardy/bikesharing/blob/main/resources/trip_duration_by_gender.png)

- When we break down the first visualization by gender, we notice similar usage patterns persist.  Usage for all genders crests at around 5 minutes, then tapers off dramatically.  After around 50 minutes or so, only a few hundred users are riding the bikes.

### Checkout times per Week Day

![heatmap_all_users.png](https://github.com/ZeroDarkHardy/bikesharing/blob/main/resources/heatmap_all_users.png)

- The heatmap shown above tracks the density of bike checkouts, aggregated by hour and week day.  We can see dense usage during commute hours, during the week.  While this was expected, there are a couple of fluctations in the pattern that may warrant some further investigation:
    - Higher than average usage on Thursdays, especially in the evenings.  Is this the result of a "spare the air" initiative, or a large weekly scheduled activity of some sort?  Is street traffic particularly bad on Thursdays, and if so, why?
    - Lower than average usage on Wednesdays, particularly during the evening commute hour.  This contrasts sharply with the elevated usage on the following day, are the highs and lows related?
- Weekend usage follows a pattern of general usage during the day, between around 9am to 7pm, with slightly more usage on Saturdays than Sundays.

### Checkout times per Week Day (By Gender)

![heatmap_by_gender.png](https://github.com/ZeroDarkHardy/bikesharing/blob/main/resources/heatmap_by_gender.png)

- The above breakdown of the previous visualization suggests that the majority of users, of all genders, share similar habits pertaining to checkout times.  The light coloration on the chart showing female users is a reflection of the much smaller number of users, but the patterns of usage persist.

### Dashboard: Gender Breakdown of users (By Birth Year), Gender breakdown of total users, User Trips by Gender (by Week Day), and Breakdown of total users by User Type

![usertype_gender_use_breakdown.png](https://github.com/ZeroDarkHardy/bikesharing/blob/main/resources/usertype_gender_use_breakdown.png)

The dashboard shown above contains many relevant measurements regarding CitiBike's userbase.
- The pie chart, top right, shows the gender breakdown for all users.  We can see that the large majority of citibike's users are male.  When we look the pie chart in the lower right corner (Breakdown of total users by User type), we can see that the majority of users are subscribers, rather than one-time-users.  Comparing these, we learn that the bulk of CitiBike's users are Male Subscribers.
- The top left series of area charts show the density of CitiBike's userbase, broken down by gender and birth year.  The data count seems to crest, for all users, around the year 1990, and then falls off dramatically.  This is a bit odd, since this data was collected in 2019, which means that the bulk of the program's users are 29 and older.  Even if we assume that a user must be at least 16 to utilize the program (the latest recorded user birth year is 2003), there is a huge drop off in users between the ages of 16 and 29 (most notably between ages 16 and 21).  
- The heatmap shown at bottom-middle of the dashboard shows patterns of usage by week day, broken down by gender and usertype.  While the portion showing data for male subscribers seems to confirm our previous findings regarding usage during week days (particularly the above-average utilization on Thursdays), one other important thing is clear:  CitiBike doesn't allow its subscribers the option not to disclose their gender, or elect a third/non-binary option.  This makes it fairly difficult to compare the data between customers and subscribers, but we can gleem from the slightly elevated usage for customers of "unknown" gender on Saturdays that the weekends see more single-use customers.  We can infer from this that users who rely on the bikes for commute purposes are more likely to be subscribers.

---

## Deliverable 3: Create Tableau Story to combine visualizations

[Click here to view the interactive Tableau Story](https://public.tableau.com/app/profile/matthew.a.hardy/viz/CitibikeChallenge_16434005025880/NYCCitibikeAnalysis?publish=yes)

---

## Summary

