## Proposal
Title: Project 1- (National Health and Nutrition Examination Survey (NHANES) 2017-March 2020 Pre-pandemic)
Members: Jim Pieper, Brittany Thomas, Caleb Cutrer, Melissa Judy

Focus: Analyze variables that impact an individual’s health. We plan on combining several datasets found on this website, including demographics, physical activity, sleep disorders/habits and prescription medicine use. The NHANES 2017-2020 survey reports health and nutrition information from adults and children obtained through direct evaluation and questionnaires. This approach from the CDC provides data from a large representation of the American population.

Research questions to answer: What conclusions can be drawn about external and internal forces on sleep patterns in the U.S. population?

Limitations: These data points were partially collected during the Covid-19 pandemic and therefore have limited information from the latter part, 2019-2020, when compared to information collected between 2017-2019.

Why: Healthcare is expensive and if there are ways to identify correlations between different attributes within a population subset, it provides an opportunity to create preventative plans.  It could benefit those who suffer from illnesses, as well as the whole of society.  Healthcare providers could plan better, educators could help establish healthy habits earlier, and families could be aware of genetic predispositions and other risk factors.   
Dataset used: NHANES 2017-March 2020 Pre-pandemic
https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?Cycle=2017-2020
“Demographics” “Prescription Medication” “Physical Activity” “Sleep Disorders”

Goal: By using well sourced data from the CDC, we will look for connections in the data regarding indicators that might lead to a better understanding of sleep patterns for people. 

## Process: 
After the group spent time looking at a variety of online datasets regarding sleep, we found the CDC's website and the NHANES.  As a group we chose a few demographic points we thought would tell a story when compared to sleep habits.  Our initial interest included more options than our final dataset used.  
The first step of data cleaning was finding a way to read the information from the CDC's website into a useable CSV.  Caleb exported out the main data and meticulously merged three different sets (demographics, medications, and sleep disorders) into one file.  He was able to rename column headers into understandable titles, too.  This was then uploaded to the GitHub main for us to use.
One noted issue was the incorrect formatting of some variables.  Instead of the 0-9 values it showed in the original file for feeling tired, the information was displayed in scientific notation.  Brittany spent a lot of time figuring out how to export the original information again, but with the values formatted correctly.  She used an XPORT function to .... FILL IN HERE.  Moreover, there were duplicates because some respondents take more than one medication.
We now had the corrected and cleaned dataset to start analyzing.  As a group, we chose different elements of demographics and medication to focus on, while all comparing it to sleep factors.  Because of this, we took different approaches to refining the original cleaned dataset to meet our needs.  This includes creating dictionaries for categorical variables, binning ranges, and adding/dropping columns as necessary.  

## Research questions to answer:
Our focus revolved around sleep: amount (hours) of sleep during the work week, amount (hours) of sleep during the weekend, feeling tired during the day (self-evaluation), and whether or not the respondent told a doctor about sleep concerns.
With a list of sleep factors to use, our goal was to look at specific demographic elements in comparison to these sleep factors. We were hoping to find connections between measurable factors like age, race, activity levels, gender, and number of perscriptions and their effects on sleep.  
If there are connections or patterns, it could help others understand or plan for potential sleep disruptions.
 
1. What conclusions can be drawn about external and internal forces on sleep patterns in the U.S. population?
2. Is there a connection between age and sleep hours? Does the average sleep duration seem differ among different age groups?
3. Is there a connection between race and sleep hours? Does the average amount of sleep different races get affect their willingness to speak to a doctor about sleep disorders? 
4. Are there any conclusions we can make regarding gender and time of sleep duration?
   
## Analysis:
In regards to prescription meds and its impact on sleep ....

Gender differences revealed a .... impact on sleep patterns ....

Race had limited patterns when comparing length of average sleep and speaking to a doctor about sleep concerns.  Generally speaking, across all races, fewer participants spoke to their doctor about sleep concerns no matter how much average sleep they got on work days or weekends.  For example, Black respondents slept the least average amount during the week and weekends, 7.4 and 8.2 respectively, but still were less likely to bring up sleep concerns with their doctor than to share sleep concerns with a healthcare professional.  On the other end of the spectrum, the respondents with the most average sleep during the work week were White respondents with 7.8 hours and Mexican-Americans with the most average weekend sleep at 8.8 hours, but neither group were more likely to with their doctors about sleep either.  Mexican-Americans also averaged the most vigorous daily activity and that might contribute to their longer weekend sleep times, and those respondents who were most active were significantly more likely to speak with a doctor about sleep.  This might be because they are injured or sore from exercise and it could impact their ability to get enough deep sleep.  
One potentially interesting visual to note was that respondents who are Asian we more likely to mark themselves as "never" or "rarely" feels tired during the day when they average the same amount of sleep as the other five races that were included in the study.  They averaged just above 1.33 for feeling tired (a 1.0 = Rarely, or 1 time a month and a 2.0 = Sometimes, or 2-4 times a month).  The next racial group was Other Hispanic at almost 1.7. White respondents averaged the most at nearly 2.0.

To investigate the potential relationship between age and nightly sleep duration, we binned the respondents' ages (ranging from 16-80yrs) into 7 age groups ("16-20", "20-30", "30-40","40-50", "50-60", "60-70", "70+") and calculated the average sleep hours on weeknights and weekend-nights for each group. After plotting these averages, it was observed that on weeknights, the younger age groups received the most sleep (16-20yo respondents had an average of 8.1 hours a sleep on weeknights) with subsequent groups having less and less sleep until bottoming out at 7.35 hours in the 50-60yo group. However, the average sleep hours then increased again in the oldest two groups, with those in the 70+ age group having an average of 8.07 hours on average--almost as high as the 16-20yo average. On weekends, there was a different trend: the average sleep hours were the highest for 16-20yo again, but average sleep hours for each of the subsequent age groups seemed to steadily decline. In order to test these differences in the groups' mean sleep hours seen on both weeknights and weekend nights, two one-way ANOVAs were conducted. Both tests indicated that there were significant differences in (at least two) of the group means. The ANOVA for weeknights returned an F-statistic of 51.617 (p-value = 6.56e^-63); the weekend-nights ANOVA returned an F-statistic of 74.272 (p-value = 4.66e^-91). Thus, it seems that age plays a role in the amount of sleep individuals get on average. It would be interesting to investigate these differences in a longitudinal study, as it would allow us to see if these patterns are explained by age or by other differences in the cohorts of this sample.     

### Further study of this topic:
In the future, it could be helpful to start to combine these factors and look at the difference, for example, between active, middle-aged Asian respondents compared to active, middle-aged Mexican-American respondents.  Combining factors would create a more holistic view of Americans.  


## Items in Project 1
1. Datasets folder: Inside the folder, there are the original imports from the CDC website, as well as the merged files we used for the main analysis
2. Jupyter Notebook scripts: Each group member created their own script using the base datasets and focused on comparing different elements to sleep
3. Visualization folder: Once data was formatted to meet individual needs, each member created at least one visualization for their work


