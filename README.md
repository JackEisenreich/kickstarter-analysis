# kickstarter-analysis

**Overview of Project:**

The purpose of this analysis was to determine how kickstarter campaigns faired based on 2 separate variables. Those 2 variables were the start date of the campaign and the dollar goal set forth prior to the campaign beginning. In particular, we looked at theater kickstarters as a whole for the start date portion of the analysis and we looked at the plays sub-category of theater for the goal portion of the analysis. From this analysis we were able to determine trends within the data to see whether it is more beneficial for the campaign to start at a particular time of year and which goal range is most likely to lead to a successful campaign.

**Part 1 Analysis:**
There were 2 parts to this analysis. The first was to look at the success of theater kickstarters based on seasonality. We did this by creating a pivot chart with parent category and years as filters, outcomes in the columns category, date created in the rows category, and count of outcomes as the values (as seen below).
 
![Pivotchart edit](https://user-images.githubusercontent.com/95661553/147416628-6b1f4fd0-b8dd-40b0-a143-cf4ba38fa42f.png)
 
Years was not an original category that we had based on previous analysis so we had to create a new column in the underlying data using the Years() function in conjunction with the date created conversion category. We also filtered on theater in the parent category so we could just analyze those kickstarter challenges. Using this pivotchart we were able to determine that May is the best month for successful kickstarters as there are 111. There are also the most kickstarters created in May. On a percentage basis, May is the month where a theater campaign is most likely to be successful. Furthermore, December is the month where a kickstarter campaign is most likely to be unsuccessful.

 
![Month Outcomes Dec   May](https://user-images.githubusercontent.com/95661553/147416654-4951ba0b-8f5d-428d-b90d-cd7abd47c93a.png)

**Part 2 Analysis**
In the second portion of the analysis, we looked at the number of successful, failed and canceled plays based on their starting goals. To do this, we first created bins by dollar amount.

 ![Goal Bins](https://user-images.githubusercontent.com/95661553/147416674-23e7bb23-eeeb-4480-9779-9ef2d98eafb5.png)

This allowed us to categorize the successful, failed and canceled within these bins and get counts for each. We did this using the countifs function: 
=COUNTIFS(Kickstarter!$D$2:$D$4115,"<1000",Kickstarter!$R$2:$R$4115,"Plays",Kickstarter!$F$2:$F$4115,"successful")
This particular countifs formula yielded the number of successful plays that had a goal of less than $1000. By changing the criteria, we were able to successfully count all the possible outcomes. We then took these numbers and divided them by the total to get the percentage successful, failed, and canceled for each bin. From this we could see that although there were the greatest number of successful plays in the 1000 to 4999 bin, the highest percentage of successful plays was in the less than 1000 bin.

**Challenges:**
The main challenge that I confronted was changing the countifs criteria efficiently and correctly. Each time I had to change the criteria I had to do so manually. I had to do this very carefully because any error here would lead to incorrect analysis. There was no way around this based on the way we were instructed to complete the challenge (at least that I could find). A better way to do this would be to create the bins better. The bins in this exercise were strings (i.e., 1000 to 4999). If we split these into 2 labeled columns with 1000 in one column and 4999 in another column then we could just reference those cells and drag down our formula each time. One more challenge faced is the actual analysis of the theater outcomes by launch date. We only determined nominal numbers and never made percentages like we did for the goals portion of the analysis. If we creted percentages we could see what time of year it better for launching a successful kickstarter.

**Results**

**Theatre Outcomes Results:**
From the analysis performed, we can conclude that seasonality greatly affects when theater kickstarters are launched and their successfulness. May and June had the highest number of theater outcomes launched an the highest number of successful kickstarters while November and December had the least. More broadly, the early summer months were more popular in launching theater kickstarters and more successful in completing their goals than the kickstarters launched in the winter months. One more conclusion that can be drawn, is that the percentage of successful outcomes does not waiver all that much. Most of months have a successful percentage of around 60% (all except December). This tells us that the biggest driver of successful campaigns is the number of campaigns (and maybe avoid launching a campaign in December).

**Outcomes based of Goals Results:**
My main conclusion about the outcomes based on goals is that the lower the goal, the most likely it is to be completed. The less than 1000 and 1000 to 4999 bins were the only 2 bins with successful completion rates in the 70s. This is also with a larger sample size than the bins with larger goals which adds credibility to that conclusion.

**Limitations:**
There are some limitations with the 2 datasets. First of all, there are some kickstarters that had incredibly small windows for raising money. One was actually just over 1 day. I think that it might be beneficial to standardize the windows because this could lead to better results. Within our analysis we are also looking at all countries on aggregate. Most of these countries are in the northern hemisphere where its summer months are June – August. We are considering some southern hemisphere countries but way fewer. If we are trying to determine the difference between successful kickstaters in the winter and summer months, we would have to take this into account in our analysis. One last limitation is the sample size for play kickstarters with higher goals. There are very few kickstarters greater than $25000. For these bins, the percentages may not be the most accurate because of this and the conclusions not as valid.

**Recommendations for different tables & graphs:**
I think that it would be beneficial to see the bar graphs of both datasets. We could see the successful, failed, and canceled results side by side and it would be easier to see the differences on a per month or per bin basis. It would also be beneficial to filter through the years on the outcome by launch date. This way we could see if there are any outliers skewing our data.


