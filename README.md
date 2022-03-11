# An Analysis of Kickstart Campaigns
## Overview of Project
Performing analysis on Kickstarter data to uncover trends in relation to cancelled, successful, and failed campaigns. Supporting data includes the goal amounts, launch dates and percentage of successful, failed, and canceled campaigns to futher explain when the best time to launch a new campaign in order to get the most profit.

## Data Analysis
### Outcomes Based on Launch Date
Data for theatre outcomes according to the launch date was input into a table to organize the campaigns according to the theatre genre and what month the campaign occurred. 

![Theater Outcomes Based on Launch Date Chart](Resources/Theater_Outcomes_vs_Launch.png)
### Outcomes Based on Goal
Next, number of successful, failed and canceled projects were pulled from the Kickstarter tab based on their goal amounts and placed in a table for reference. From the pulled data, the percentage of those projects were calculated and an *Outcomes Based on Goal* line chart was made to give an idea of how successful each project was based on their goal amounts.

![Outcomes Based on Goal](Resources/Outcomes_vs_Goals.png)

### Challenges Encountered
The `COUNTIFS` formula that was used for the chart *Outcomes Based on Goal* was a tricky one, you had to have the formula just right to return the correct data. There are three different columns that were used to get the amount of plays in each outcome status, if these are not just right the numbers were skewed and they wouldn't make much sense. One main item to remember is to use the goal column data instead of the pledge column.

## Results
### Results on Outcomes Based on Launch Dates
Based on the chart created from the table data for the *Theater Outcomes Based on Launch Date*, it is best to launch a campaign in May or June in order to get the best possible outcome. 
Also, we can assume that September through December seems to be the worst time to launch a campaign, highlighting that in October was the highest in failed campaigns.
### Results on Outcomes Based on Goal
Looking at the *Outcomes Based on Goal* chart, we can conclude that highest successful campaigns have a goal of less than $1,000; whereas the lowest successful campaigns lie in the $45,000 to $49,999 goal range. 

### Links to Code
To calculate the number of successful, failed, and canceled plays based on goal amount the following formula was used: 

`=COUNTIFS(Kickstarter!$D:$D, "<1000",Kickstarter!$F:$F, "successful",Kickstarter!$R:$R, "plays")`

Each number is updated according to each goal threshold to return the correct number, for example, the above forumla returns the number of plays with a goal of less than $1,000.

The number of total projects was then totaled using the `Sum` function.

To get the percentage of Successful, Failed, and Cancelled, the following formula was used:

`=ROUND(IFERROR(B2/E2,0),2)`

This formula divides the number of successful (or failed, cancelled) by the total number of projects and outputs the result in a percentage.

The `IFERROR` function was nested into the formula to correct any data that had a zero in the calculation; instead of displaying an error, it would display the answer as zero.

### Limitations in the Data Set
One limitation could be how the advertising was handled. Were certain age groups targeted? What platforms were used to advertise the plays? Did they depend on word of mouth of others?
Another limitation is what time the play was offered, does it take place in the morning or afternoon? Were there times that were more successful than others?

### Other possible Tables and Graphs 
A chart of the play's country could be compared with the goal and/or pledged amounts to see what regions have the best outcome.
