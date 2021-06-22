# Kickstarting with Excel 
**Fever's Fundrasing**
## Overview of Project
After working with Louise, she nearly has met her fundraising goal for her play Fever quickly. As she gets ready to open, she needs to evaluate how successful different campaigns were by funding and The data of opening. Once we evulate the best opening time, we need to also look at the goal amounts. If we compare the goal amounts for the for failed, successful and canceled campaigns, we can use the numbers to adjust the campaigns goal amount. We can then present our findings through visuals. The overall goal of this analysis is to give Louise the best date to open her play and confirm the amount she needs to have through funding to be successsful with her play Fever. 

## Analysis and Challenges
To begin with on this challenge, I needed to focus on the dates the campaigns were opened. During our previous analysis, the numbers in j and k were converted to dates in columns R and S. However, this has not provided us with year or monthly trends.  In order to uncover peak successful months, peak failed months and trends within the canceled plays, we needed to extract the year. The yeasr was I extracted to column t using the following formula **=year(R2)**. 

###### Pivot Table
Now that the years were seperated I wanted to use a pivot table to look at the number trends for date converted dates and show it for the categories of successful, failed and canceled. For the pivot table I started by putting the outcomes in the columns section so we could see each outcome. Next I added the date converted conversion column to the Rows section.I then removed the years and full date to leave the months showing. This allows us to see the peak months. Then, in the values section I also added the count of outcomes so we could look at the sums of outcomes in each of the successful, canceled and failed columns.  Now as were are dealing with a play, we would want to filer our data for theatre. The final filter was years so we can evaluate if trends havew changed over the years. I also added the visual of a pivot chart to see the peaks for each outcome.**See png Theatre Outcomes by Lauch Date**

### Analysis of Outcomes Based on Launch Date
After analyis I can conlude that the peak month for the most successful openings were in May. While, the failed outcomes showed a peak in October. Unfortunatly, there was not enough data with the canceled outcomes to see any trend lines. 
### Analysis of Outcomes Based on Goals
The next set of data we wanted to analyize to assist Louise's campaign was to provide a set of goal perametersin terms of money raised and compare that to the number of successful, failed and canceled campaigns. To begin with our goal perameters were set to:
-Less than $1000
-$1000 to $4999
-$5000 to $9999
-$10000 to $14999
-$15000 to $19999
-$20000 to $24999
-$30000 to $34999
-$40000 to $44999
-$45000 to $49999
-Greater than $50000
Using my set perameters, I started by analyizing each campaign using the countifs formula.  For the first column B I used the formula **=COUNTIFS(Kickstarter!D:D, "<1000", Kickstarter!$G:$G, "successful", Kickstarter!$P:$P, "plays")**.
 As A2 onl had one range I set it to "<1000". Now when dealing with a range of numbers the formula was updated to reflect **=COUNTIFS(Kickstarter_info!D:D,">=1000", Kickstarter_info!D:D, "<=4999", Kickstarter_info!G:G,"successful",Kickstarter_info!P:P,"plays")**. Going down column A:A the formula was changed to reflect each range of numbers. Now for the last formula I updated it back to the original formula used in B2 and changed the dollar amount to 50,000. 
 **=COUNTIFS(Kickstarter_info!D:D,">50000",Kickstarter_info!G:G,"successful", Kickstarter_info!P:P, "plays")**
 The formula was copied columns C:C and D:D and the second range was updated to look for "failed" and "canceled" outcomes. 

Once I had calculated the goals in column A:A for the successful, failed and canceled campaigns, I wanted to know the total for each earnings bracket. ***Using the autosum formula I added (B2:D2).*** This was repeated horizontally across each earnings line.

From the data I uncovered that campaigns that the successful ones had a 50% chance of suceeeding, but also a 50% change of failing. 
### Challenges and Difficulties Encountered
The challenges were the line chart for the Outcomes based on Goals. I struggeled with the formatting. I would like to further analyize this with a bar chart. 
## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
I can conclude that she should lauch at May 
She should also have a positive outcomes with 111% fund backing. 
- What can you conclude about the Outcomes based on Goals?
I can comclude that they goals need to be over 50,000
- What are some limitations of this dataset?
The number of kickstarters and the lenth of time. 
- What are some other possible tables and/or graphs that we could create?
I would create a box plot to uncoverer the mean, median and mode of each outcome. Furthermore, with a boxplot we can see the Interquartile range and see whether the data is right or left skewed. I would use the  scatter plot to analyize the yearly trends.