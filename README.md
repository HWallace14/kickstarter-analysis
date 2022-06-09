# An Analysis of Kickstarter Campaigns

Performing data analysis on Kickstarter to uncover trends

## Overview of Project

### Purpose

The purpose of this project is to help our up and coming playwright, Louise, discover whether or not a Kickstarter for her passion project would yield beneficial results. In order to do this we first looked at the outcomes of theater Kickstarters based on when they lauched and then we looked at the outcomes of different types of Kickstarters.

## Analysis

### Analysis of Theater Outcomes Based On Launch Date

Looking at the graph below we can discern that the best time to launch a Kickstarter for a play would be May through July as they have the highest rates of success. We can also tell that the worst times to launch a Kickstarter for a play would be November and December.

<img width="311" alt="Outcomes Based On Launch Date Chart" src="https://user-images.githubusercontent.com/105998378/172029300-8859b515-e426-4147-9004-932575c68bdc.png">

### Analysis of Outcomes by Parent Category



<img width="302" alt="Parent Category Outcomes Chart" src="https://user-images.githubusercontent.com/105998378/172029394-3a0aeb25-bd06-4ce5-b7b2-36344131ffa7.png">

---

# Kickstarting with Excel

## Overview of Project

### Purpose
This analysis was performed in order to help our client, Louise, figure out how different campaigns fared in relation to their launch dates and funding goals. This was inspired by her rapid success in funding her own play "*Fever*," which led to her desiring to see how she stacked up against other plays.
## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
We began by first using the `=Years()` formula to figure out which year each kickstarter was launched. This would be useful for later on when filtering through years to determine if there was a yearly trend or if it the results were typical year-over-year. We created a new column titled, appropriately, "Years" and then used the Years formula on column S with the converted launch dates of each kickstarter to determine the year each was launched.

We created a pivot table using this new data as well as all of the original Kickstarter data and used the filters Parent Category and, as stated previously, Years. We used Outcomes for our columns and removed the "Live" and "Blank" outcomes as we did not want to confuse the chart with outcomes that had not been determined yet. This was confusing for me originally as I had forgotten that there were live Kickstarters and was unsure where the "blanks" had come from, so they made my table look different from the example.

We also used Outcomes for the Values field, which gave us the count of each value "successful," "failed," "canceled." Finally we used the Date Created Conversion field for our Rows, but we had to remove the year and day because it confused the chart too much and, as stated above, we could simply filter for year if we wanted to find a trend there. It took me a minute to realize that the example was filtered by month only and it took me even longer still to realize what needed removed to get that result.

After all was said and done we created a line chart with markers to notate the months from the pivot table that we had crafted and saved that chart for future examination. 

<img width="307" alt="Theater_Outcomes_vs_Launch" src="https://user-images.githubusercontent.com/105998378/172455280-501883eb-845c-48e9-9ede-9de0befee69a.png">

### Analysis of Outcomes Based on Goals
To find outcomes based on goals we had to do a little paring down of the data into more easily digestible bits. 

First we gathered the number of successful, failed and canceled projects by goal range, splitting the ranges from less than to one thousand to 1000-4999, then 5000 to 9999 and so on until we got to 50000 or more. We did this by using the `=COUNTIFS()` function to search for the outcome, subcategory and dollar range that we wanted in the Goals column. I had some issues with mixing up ">=" and "=>" that caused me to get incorrect results for a time but everything worked out once I realized my mistake. 

We then summed the different outcomes for each goal range to get a total number of kickstarters in each range. This allowed us to divide the number collected by our `=COUNTIFS()` with the total to get a percentage of each type of outcome. Using just the percentages and the goals we created a line chart that represents the outcomes in each range by percentage of the whole.

<img width="573" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/105998378/172455463-af7b0294-66af-4311-b729-dae9cbb1cc8b.png">

### Challenges and Difficulties Encountered
In the "Outcomes Based on Goals" section of the unit I found that Excel is very picky when it comes to particular formulas. Instead of putting ">=" in my COUNTIF formulas I typed "=>" which, to anyone speaking the phrase, would mean the same thing. Excel, however, did not recognize my particular formula and so returned all of my equations with the value 0. After staring at the formula for a minute and realizing that it wasn't right I switched the two values and started getting results that were not 0. 
## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

The first conclusion I can draw from the Outcomes Based on Launch Date is that, if I want to have a successful Kickstarter for a play, I should plan it around the May-July period.

The second conlusion I an draw is that I should avoid creating a kickstarter for plays August-April. The success rate for those months is less than ideal and sometimes is less than half of May-July period.

- What can you conclude about the Outcomes based on Goals?

I can conclude that the goal range doesn't seem to really affect the success rate until you get to the $45,000+ range and above. There are kickstarters that had goals of $35,000-$44999 that succeeded while others in the $25,000-$34999 range failed. We even see success rate of $5,000-$9,999 barely staying above 50%, which leads me to believe there is some other factor at play other than the goal range. 

- What are some limitations of this dataset?

The dataset doesn't take into account the available ecess money for each area. For instance what is during these time periods there was a recession in the US but not in GB? It also doesn't show how much the budget for marketing each idea was. If someone's spending $10k on marketing their kickstarter with a professional company versus someone else who's used $500 and did their video themselves, that might affect the amount a donor would donate or if they would even donate at all.

- What are some other possible tables and/or graphs that we could create?

We could create a table/graph comparing staff pick status and outcomes. Similarly, we could see if there's a correlation between a Kickstarter being spotlit and its outcome. We could try and find out which type of kickstarter has the most success in each country. Or we could just pick a country and see which type of kickstarter was most successful. 
