# Kickstarting with Excel

## Overview of Project
This fundraising analysis project utilizes data produced from the various outcomes of Louise's performance campaigns and is then entered into Microsoft Excel to find correlations and possible conclusions from the analysis. There are various elements that contribute to both the success and shortcomings of Louise's campaign; elements such as funding goals, amounts funded, number of supporters, type of performances, location, and launch date, to name a few. Taking these outcomes and values and combining them with the analytical tools found in Excel, conclusions can be made to help Louise determine what campaigns were successful, but most importantly, what factors helped in creating a strong campaign. 

## Purpose
The intent of this analysis is to assist Louise in evaluating how successful and unsuccessful her play campaigns performed in relation to the funding goals achieved, and the date that a specific campaign was initiated.

# Analysis and Challenges

## Analysis of Outcomes Based on Launch Date
![Line chart displaying Theater_Outcomes_Based on Launch Date](https://user-images.githubusercontent.com/90368828/134102309-12a1f0a0-a504-4b85-bda3-8617d04946ca.png)

When looking at the outcomes of theater campaigns based on the campaign launch date between the years of 2009 and 2017, all three outcomes follow a predictable pattern that is in line with social occurrences, events and holidays that occur throughout the year.

Beginning with successful outcomes, the lowest point of successful campaigns is in the months of November & December, with 54 campaigns in November and decreasing to 37 campaigns in December. A possible explanation for this could be because these are the holiday season months when families are celebrating at home or visiting relatives. Moving on to the months of March through May, a sharp increase can be seen here possibly resulting from students being out of school for summer break, and adults beginning to take time off in order to enjoy theater performances as a family activity.

The decrease beginning in June and continuing through August, and finally reaching a low in September, can be due to theatergoers finding other activities to do during the summer months, as well as students returning to school in August & September (maybe even in late-July for some schools).

Moving onto the failed campaign line, it follows an interesting formation that mirrors the successful campaigns above it. A glance at the month of May produces the highest number of failed campaigns which is also the highest number of successful campaigns. The same peaks can be seen in February and October where both the failed and successful lines slightly peak up from the respective previous month. Continuing with the mirrored chart activity, both successful and failed campaign lines take similar dips in March, September, and November.

The soundest reasoning for these increased mirrored peaks is that, as there are more campaigns being launched, the chance of failure goes up as well, which can be seen in February, May, and October. The same theory could be applied to the decreased mirrored peaks in March, September, and November; since there are less campaigns being launched, the chances of failure increase due to these campaigns not yielding successful results during these time periods.

Finally, the canceled line has a straightforward explanation due to fact that cancellations would be based on personal reasons pertaining to Louise. The highest number of cancellations can be seen in January with a total of 7 canceled campaigns. It would be safe to assume that since this is the beginning of the year, Louise may have had to cancel performances to work on other more important campaigns, or to reallocate assets to fund different projects.










## Analysis of Outcomes Based on Goals
 ![Line chart showing Outcomes_Based on_Goals for the 'play's subcategory](https://user-images.githubusercontent.com/90368828/134102388-7c2cf5d3-cb08-4464-b7e6-7f29838fc505.png)


The outcome of play-type performances in relation to goal amounts portrays an interesting inverse relationship between the percentage successful and percentage failed chart-lines.

It seems that the overall trend is that as a play’s goal becomes more expensive in funding, the less successful it becomes. For example, plays that took less than $1,000 in funding had the highest success rate of 76%. But as the funding requirements reach between $15,000 and $19,999 the success and failure rates intersect at 50%, and the plays requiring higher funding begin displaying a pattern of diminishing returns.

Between the funding amounts of $20,000 and $34,999 is where we can see a large inverse formation between the success & failure rate. But there is an even larger inverse pattern when funding requirements reach between $45,000 and $49,999. Therefore, corroborating the theory that a higher funding goal amount decreases a project’s success rate, and increases its failure rate.

An interesting section to examine is between the amounts of $35,000 and $44,999 where the theory is not substantiated and takes a different formation. Although this is shown, what must be taken into consideration is the population size of projects within this goal range. Within the $35,000 to $39,999 and the $40,000 to $44,999 ranges, they have total project amounts of six and three, respectively, and both share a two-thirds success rate, or 67%. Because of the lower total project amount, it made it easier for a higher success rate achievable for these goal ranges.

Finally, as for the percentage canceled line, it rests at 0% due to the fact that ‘canceled’ is not an available outcome for the ‘plays’ subcategory. 



## Challenges and Difficulties Encountered
Throughout the analysis, one of the initial challenges I encountered was with constructing the PivotTable for the ‘Theater Outcomes Based on Launch Date’ section. I was able to put together three quarters of the table: filtering by ‘Parent Category’ & ‘Years’, ‘Outcomes’ in columns, and ‘Date Created conversion’ in rows. At this point, the PivotTable I had constructed with this setup produced a table very similar to the template table shown in the module challenge, but I was missing all the values for the outcomes. I was stumped at first, but I decided to attack this issue by trial and error. I knew I needed numerical values for the outcomes, so I just inserted ‘Outcomes’ into each field until I achieved the correct results with placing ‘Outcomes’ into values to get the ‘Count of Outcomes’, which resulted in showing all the numerical values for the outcomes.

Although I approached it with a trial-and-error style, I took a moment to reflect what it really meant to have outcomes in the values section. Placing a specific field in values is helpful as an analytical tool because you can summarize a field’s value by the total sum, average, max & minimum values, and the standard deviation, to name a few. This offers different analytical perspectives on a certain set of data which can help one reach different conclusions about a dataset.

The only other challenge I stumbled upon was with the ‘=COUNTIFS(‘ function for the number successful, number failed, and number canceled columns. Just like ‘Theater Outcomes Based on Launch Date’ section, I was so close to having all the correct filters in place to get the correct output for each outcome, but I was not quite there yet. Using the $1,000 to $4,999 goal range and the ‘successful’ outcome as an example, my initial count-if function for the outcome is shown below:

**=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$F:$F,"successful",Kickstarter!$D:$D,"<=4999")**

The obvious mistake here is that I forgot to filter by the subcategory type in column O. My thought process for this was that, if the sheet which the data is referring to is filtered by that specific subcategory, the numbers outputted would be reflective of what has been filtered. But this was not the case because the line chart that was produced with this initial function line was nothing close to the chart that was shown as the solution within the module. From here, my next course of action was messing around with the filter in column O to see if it would change the outputted amount, which it did not.

This is when I realized that my initial theory was incorrect, and took a long, hard look at the function and came to the revelation I would need to include an additional command to filter out the results. By reviewing the function repeatedly, it helped me understand what the function is a form of a conditional statement that has parameters set by yourself to produce the results. At this point, I was able to formulate this snippet to be added at the end of the function:

**Kickstarter!$O:$O, "plays"**

With this additional filter created, the entire function for the example above looked like this:

**=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$F:$F,"successful",Kickstarter!$D:$D,"<=4999",Kickstarter!$O:$O, "plays")**

After adding this additional piece to all the different goal ranges for each respective outcome, I started noticing that the count of the outcomes was changing, which inherently changed the total projects amount, and all the percentages that followed. Finally at this point, the outcomes based on goal chart reflected the exact pattern that the template chart exemplified for the challenge.

## Results

- **What are two conclusions you can draw about the Outcomes based on Launch Date?**
The first conclusion that can be seen with the Outcomes Based on Launch Date is that there is a correlation between when the launch date occurs, and how successful a theater campaign can be due to the social occurrences, events and holidays taking place in specific time periods. For instance, there were a lower number of successful campaigns in the months of November & December due to the holiday season, when families are spending time with relatives and celebrating at home. Another conclusion that can be drawn from this analysis, is that as more campaigns succeed, the number of failed campaigns increase as well. This can be seen in the month of May where there is spike in failed campaigns which correlates with the large increase in successful campaigns, which is also seen sporadically in February and October.

- **What can you conclude about the Outcomes based on Goals?**
The Outcomes Based on Goals for the ‘plays’ subcategory portrays an inverse relationship between the success and failure rates for the plays which is exemplified in the line chart created for the analysis. This inverse relationship is influenced by the funding goal amounts, as the amount needed increases, the failure rate increases due to the higher amounts. An exception to this theory is exemplified between the amounts of $35,000 and $44,999 where the success rate switches momentarily with the failure rate due to a smaller population size of total projects for this particular funding range.

- **What are some limitations of this dataset?**
One possible limitation of the dataset is that it does not take into consideration the average age of the theatergoers attending Louise’s performances. An additional piece of data like this would be beneficial especially for the ‘Theater Outcomes Based on Launch Date’ analysis because it could possibly further corroborate the stated theory regarding the outcomes based on launch date. For example, during the earlier summer months, it could be inferred that the average age would be lower due to more children attending these shows because of summer break. Then, for the later summer months, the average age could possibly go up due to more adults attending the shows. But, let’s say that the average age of theatergoers is a higher amount all throughout the year, it would imply that Louise’s performances are geared for mature viewers which would put the previously purported theory in question, and warrant a new theory to be sought for.

  Another limitation of the dataset is a factor that is already included within the set, which is the country of where the campaign took place. After having completed both analysis’, I realized that the country was not taken into consideration neither for ‘Theater Outcomes Based on Launch Date’ nor ‘Outcomes Based on Goals’. Using the theater outcomes as an example, including the country could be beneficial because it provides additional support for my theory regarding outcomes based on launch date. For example, filtering outcomes based only in US could provide further insight whether my theory is true or not.

- **What are some other possible tables and/or graphs that we could create?**
A possible alternative chart to use for the ‘Theater Outcomes Based on Launch Date’ that I can think of would be using a pie chart to portray the different theater outcomes. Although a bit less analytical than utilizing the line chart, it could provide a simpler portrayal of the chosen dataset. Another chart that could provide a different perspective of the theater outcomes would be a stacked bar chart. This would simplify the previously used line chart, and show how many successful, failed, and canceled campaigns occurred and how much it comprises of the total amount of campaigns.




