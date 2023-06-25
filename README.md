# Data_analysis
Data_analysis_project

# Intoduction

For the capstone project of the Google Data Analytics certificate, I have chosen the Cyclistic bike share data to work on. For the case study, I will perform real-world tasks of a junior data analyst for the marketing team at Cyclistic, a fictional bike-share company in Chicago. To answer key business questions, I will follow the six steps of the data analysis process : Ask, Prepare, Process, Analyze, Share and Act.

# About The Company

In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime. Until now, Cyclistic's marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members. Cyclistic's finance analysts have concluded that annual members are much more profitable than casual riders. Although the pricing flexibility helps Cyclistic attract more customers, Moreno believes that maximizing the number of annual members will be key to future growth. Rather than creating a marketing campaign that targets all-new customers, Moreno believes there is a very good chance to convert casual riders into members. She notes that casual riders are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs. Moreno has set a clear goal: Design marketing strategies aimed at converting casual riders into annual members. In order to do that, however, the marketing analyst team needs to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. Moreno and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.

# Scenario

The director of marketing of Cyclistic, Lily Moreno, believes that the company's future growth depends on maximizing the number of annual memberships. Hence, the marketing analyst team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, the analytics team could be able to design a new marketing strategy to convert casual riders into annual members.

Three questions will guide the future marketing campaign:

1.How do annual members and casual riders use Cyclistic bikes differently?

2.Why would casual riders buy Cyclistic annual memberships?

3.How can Cyclistic use digital media to influence casual riders to become members?

I have been assigned by Moreno the first question.

# The Ask Phase

How do annual members and casual riders use Cyclistic bikes differently?

Why would casual riders buy Cyclistic annual memberships?

How can Cyclistic use digital media to influence casual riders to become members?

Lily Moreno: The director of marketing and my manager. Moreno has initiated this strategy. The first stakeholder to deliver to.

The executive team: For Moreno´s idea to work, the executive team must approve our recommendations, so so they must be backed up with compelling data insights and professional data visualizations.

# The Prepare Phase

Data Source: Past 12 month of original bike share data set from 01/06/2022 to 31/05/2023 was extracted as 12 zipped.csv files. The data is made available and licensed by Motivate International Inc under this license.

Data Organization & Description:

File naming convention: YYYY_MM

File Type: csv format

File Content: Each csv file consist of 13 columns which contain information related to ride id, rider type, ride start and end time, start and end location etc. Number of rows varies between 49k to 531k from different excel files.

Data credibility:

The data set is reliable, the data is complete and accurate for the chosen time window.

The data is original, it is a first arty information.

The data is comprehensive, the data set contains all information needed to answer the question.

The data is current, rider data of the last 12 months was used.

The data is cited and vetted by Chicago department of transportation.

Data Security: Riders' personal identifiable information is hidden through tokenization.

Original files are backed up in a separate folder.

Data Limitations: As riders' personal identifiable information is hidden, thus will not be able to connect pass purchases to credit cards numbers to determine if casual riders live in the Cyclistic service area or if they have purchased multiple single passes.

# The Process Phase

I used R for data verification and cleaning:

Reasons: The 12 data sets combined will contain more than 5 million rows of data. Excel worksheet limitation is 1,048,576 rows. Moreover, some csv files could not uploaded to BigQuery for file size problems. Thus, R is used to perform all tasks from organizing, cleaning analyzing and visualizing data.

# The Analyze Phase

Setting up the environment

Here, I use several libraries that help reading, cleaning, organizing and analyzing the data.

First analysis step: descriptive analysis on ride length

First of all, a descriptive analysis on ride length [min] is performed.

The overall average ride length is 18.71 minutes.

Second, the mode of weekday is calculated, namely which weekday occurs the most or on which weekday most bike are rented.
![000010](https://github.com/Adarsha2002/Data_analysis/assets/91897040/c8dbe85b-5d84-46c6-beab-e12f770ef78e)

The plot shows that most rides were started on Saturday(991047 rides), Saturday(857285 rides) followed by Friday(810508 rides). So most bikes are rented on the weekend.

Next, a plot of the ride_length or average_duration in minutes for every day of the week for members and casual riders is shown.

![000010](https://github.com/Adarsha2002/Data_analysis/assets/91897040/6e846d53-4fa7-4bc9-a8f0-ef2d39dae7f3)

The plot demonstrates that casual riders rent bikes for longer durations, especially on Sunday, Saturday, Friday (weekend) and on Monday. Members show a steady riding/using behavior, plus they also tend to ride a little longer on the weekend.

Here, number of rides per day for every rider type is plotted.
![000010](https://github.com/Adarsha2002/Data_analysis/assets/91897040/7f66a6ca-f2f3-4e2e-9111-313c869c6af0)

Surprisingly, and in contrast to the former plot, members begin more rides and thus have higher number of rides on every day of the week except for Saturday and Sunday.

Second analysis step: average ride length depending on rider type and number of each rider type
![000010](https://github.com/Adarsha2002/Data_analysis/assets/91897040/178152aa-396b-4190-ad70-e3066ace0189)

So, the result shows that casual riders tend to rent bikes for longer mean durations than members (32 min to 13.6 min), in accordance with plot 2. Members probably use bikes to commute, whereas casual riders maybe, among other things, exercising, visiting the city or attending special events.

Here, the overall rider count based on rider type is plotted
![000010](https://github.com/Adarsha2002/Data_analysis/assets/91897040/96318e78-e161-4c2d-9a41-de9bbe19ddb6)

The plot indicates that more than half of all riders are member riders (3/(3+2.5)=0,55)

Third analysis step: Exploring effect of seasonality

Here, the Function "season" of the library "metR" was used to assign season to months:

DJF:winter

MAM:Spring

JJA:Summer

SON:Fall
![000010](https://github.com/Adarsha2002/Data_analysis/assets/91897040/447070fb-ecc0-4e38-a654-48c0bb098d72)

![000010](https://github.com/Adarsha2002/Data_analysis/assets/91897040/406d2961-2125-49db-816f-aafde946cd8b)

Plot 6 tells us that number of rides of members is always higher than that of casual riders on every work day in every season. Weekends are still the time where casual riders bike more than members. The only exception of this trend is in the summer months (Mar, Apr, May). Plot 7 demonstrates that the member group has all year long the average ride length of about 13.6 minutes. Casual riders use bikes about half an hour long on all days in spring and summer. In winter the average ride lengths becomes less than 30 minutes.

Lastly, let us generate a line plot for continuous change of number of rides along the whole year for the two rider types.

![000010](https://github.com/Adarsha2002/Data_analysis/assets/91897040/c03d5783-8e94-4991-80b1-5ab788ce887b)

The plot indicates, for casual riders/members, ridership peaked around Dec/January (Winter months being the turning point) and hit the lowest at May before rebounding up swiftly and continuously.

# The Share phase

## Conclusions/Summary of insights

Members and casual riders differ in how long they use the bikes, how often they use the bikes, and on which days of the week does every group peak:

Casual rides peak during weekends (plot3). There is a high probability they are tourists visiting and sightseeing the city, or that they are ordinary Chicago residents who are riding bike in their leisure time during the weekend. The longer average ride time for casual rider (plot2), also peaking at the weekend, provides evidence for this point.

Ride length for members are relatively shorter compared to casual riders. This could clarified as such, that most members use the bikes to commute on workdays. This clarification would also explain the short riding durations of members. They ride from point A to B, namely roughly always the same ride lengths and the same distance

Ridership start to pick up (plot8) from February (from Spring through Summer)and start to decrease in August (from Fall through winter). This correlation is due to the seasonal changes. As the weather start to get warmer and more pleasant in February (start of Spring), more people starts to cycle, and inversely when the weather becomes less warm cold around September (start of Fall).

More than 50% of the riders are annual members (plot5), suggesting that the company have already achieved a certain level of loyalty among its bike users. This indicates a positive message, namely that the company is going to be able to convince many casual riders to convert to members, and to keep the new members satisfied.

# Recommendations

Give discounts for longer rides when you have a membership Longer rides can get some type of rewards program when they become members

The marketing campaign should be launched between February to August, as the number of trips made by casual riders peaks at this time of the year.

As casual rider usage reach its highest point on the weekend, the marketing campaign can include weekend-only membership at a sensible price. This could attract casual riders to convert to members.

The campaign could include ride-length-based tariff plan (maybe only on weekends): Bike more, pay less ! This provides more incentive for the member rides to cycle longer distances.

Alternatively, longer rides can be rewarded with benefits such as discount vouchers.























