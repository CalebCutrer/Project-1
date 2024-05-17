## Proposal
Title: Project 1- (National Health and Nutrition Examination Survey (NHANES) 2017-March 2020 Pre-pandemic)
Members: Jim Pieper, Brittany Thomas, Caleb Cutrer, Melissa Judy

Focus: Analyze variables that impact an individual’s health. We plan on combining several datasets found on this website, including demographics, physical activity, sleep disorders/habits and prescription medicine use. The NHANES 2017-2020 survey reports health and nutrition information from adults and children obtained through direct evaluation and questionnaires. This approach from the CDC provides data from a large representation of the American population.

Main research question to answer: What patterns or correlations can be identified between sleep metrics and intrinsic vs extrinsic variables in the U.S. population?

Limitations: These data points were partially collected during the Covid-19 pandemic and therefore have limited information from the latter part, 2019-2020, when compared to information collected between 2017-2019. Not every data point was captured for all respondents (e.g. not all respondents answered all questions on the questionnaire). Therefore, the datasets used for comparison vary in sample size, leaving blank data. Pros and cons of leaving the blank data versus dropping it were discussed. Both options result in bias.

Why: Healthcare is expensive and if there are ways to identify correlations between different attributes within a population subset, it provides an opportunity to create preventative plans and mitigation strategies.  It could benefit those who suffer from illness, as well as the whole of society.  Healthcare providers could treat patients optimally, educators could help establish healthy habits earlier, and families could be aware of  predispositions and other risk factors. Sleep is an important factor in determining overall health. Understanding the specific factors that influence sleep behaviors and quality could provide specific strategic approaches to further support optimal health.  

Dataset used: NHANES 2017-March 2020 Pre-pandemic
https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?Cycle=2017-2020
“Demographics” “Prescription Medication” “Physical Activity” “Sleep Disorders”

Goal: By using well-sourced, reputable and current data from the Center for Disease Control, we will perform exploratory data analysis to make interesting observations, connections and correltations between intrinsic and extrinsic variables that may lead to a better understanding of sleep habits in individuals. This provides a foundation for further exploratory data analysis.

## Process: 
After the group spent time looking at a variety of online datasets regarding sleep, we found the CDC's website and the NHANES. As a group we chose a few demographic points we thought would tell a story when compared to sleep habits.  Our initial interest included more options than our final dataset used.  


We now had the corrected and cleaned dataset to start analyzing.  As a group, we chose different elements of demographics and medication to focus on, while all comparing it to sleep factors.  Because of this, we took different approaches to refining the original cleaned dataset to meet our needs.  This includes creating dictionaries for categorical variables, binning ranges, and adding/dropping columns as necessary.  

### Data Export
The first step involved downloading the datafiles from the CDC website and uploading to GitHub. The CDC website includes direct links to export datasets without the use of an API key. The datasets are .xpt files and therefore some exploration was needed to convert them to a usable format, such as csv. Once the .xpt files were downloaded, pandas was used to read in the files using pd.read_sas. Caleb meticulously merged three different sets (demographics, medications, and sleep disorders).  The final merged dataset was read in as a csv file. This was then uploaded to the GitHub main for group use. A .gitignore file was created. The code for this work is found in FinalMerged.ipynb.

### Data Cleaning
Caleb further cleaned the data by renaming all the variables for readabiilty. The dataset was trimmed to 15560 rows across 15 columns.

Melissa created dictionaries to re-code numerical variables into categorical variables (e.g. for the race category the dictionary recoded 1.0 : "Mex-Am"). Melissa further cleaned the merged data by dropping unnecessary columns based on the focused analyses we were planning. The code for this work is found in FinalMerged.ipynb.

### Data Debugging
During review of the data, Brittany noticed the data in the SLQ120 column (later renamed to "Feeling Tired During the Day") was exporting exponential values instead of integers which was the expected format. Several hours were spent exploring possible causes, such as column formatting, encoding keys, exporting issues, etc. A resource about SAS XPORT file readers and the xport module was provided by the TA. In reading this, the recommendation was to install the program xport and try re-reading the sleep disorders data with the xport program. This was successfully done by installing xport (pip install xport == 2.0.2). See visual of this in the Visualizations folder. As there was an issue installing the xport module in pandas, the Sleep Disorders .xpt file was converted to csv using the command line (outside of pandas): python -m xport Sleep_Disorders.xpt > Sleep_Disorders_2.csv. The csv was then uploaded to github, read in using utf-16 encoding key (as recommended on Stack Overflow for .xpt files) and merged with the main dataset. The utf-16 and xport modules fixed the formatting issue. This work is documented in Sleep_Data.ipynb.

Brittany performed a data check to compare the observed number of responses for each variable to the expected number of responses published in a summary on the CDC website. Noticing discrepancies and at the same time noticing the Respondent ID was repeated more than once in several dataframes, a duplicative entry issue was identified. When the data was merged, it was merged based on SEQN (Respondent ID) which was assumed to be a unique identifier universal to all datapoints. However, in the prescription medications dataset, respondents were asked how many prescription medications they take and for each one how many days they are taken. This introduced multiple entries for a given respondent and duplicated rows of data for the entired merged dataset. Multiple solutions were considered. The most straightforward solution was to eliminate all duplicates based on SEQN (Respondent ID) given that this would not eliminate data that we were intending to analyze. It would have implications for future analysis if "number of days taking medication" data was planned for analysis. This work is documented in Data_Remove_Dups.ipynb.

With corrected and cleaned datasets to start analyzing, we chose different elements of demographics, physical activity and prescription medication to explore, while all comparing it to sleep factors.  Because of this, we took different approaches to refining the original cleaned dataset to meet our needs.  This included creating additional dictionaries for categorical variables, creating variables to condense code, binning ranges, and adding/dropping columns as necessary.  


## Research questions to answer:
Our focus revolved around sleep: amount (hours) of sleep during the work week, amount (hours) of sleep during the weekend, feeling tired during the day (self-evaluation), and whether or not the respondent told a doctor about sleep concerns.
With a variety of sleep factors choose from in the CDC dataset, our goal was to look at specific demographic and behavioral elements in comparison to these sleep factors. We were hoping to find connections or correlations between measurable factors (like age, race, activity levels, gender, and number of perscription medications taken) and their effects on sleep.  
 
Main Research Question: What observations, patterns and correlations are evident when comparing intrinsic and extrinsic variables on sleep duration and/or frequency of tiredness in the U.S. population?
1. Are there observations or correlations that can be identified within the sleep disorders dataset by itself?
2. Is there a connection or correlation between age, race, prescription medication use or gender and sleep hours?
3. Does the average sleep duration seem to differ among different age groups?
4. Does the average amount of sleep different races get affect their willingness to speak to a doctor about sleep disorders?
5. What conclusions can be drawn from the above observations and correlations?

Observations and cconnections between variables could help healthcare providers, government agencies and educators identify and address potential issues that negatively impact sleep outcomes.
   
## Analysis:
#### Sleep Data Analysis
Reported hours of sleep during the week vs the weekends were binned into 4 categories based on the unique entries provided by respondents over a range of 2-14 hours. Four groups were created that included short (2-5hrs), moderate (5.1-8hrs), long (8.1-11hrs) and extensive (11.1-14hrs) sleep duration. A plt.subplots function was used to graph two pie charts side by side to compare sleep hour distribution during the week vs during the weekend. As predicted, a larger proportion of respondents reported sleeping "long" hours duirng the weekend compared to during the week (29.6% vs 45%). There were fewer respondents that reported short sleep durations during the weekend than the week, also as predicted. A statistical analysis was performed comparing duration of weekday sleep and frequency of feeling tired during the day. An ANOVA analysis showed a statistically significant correlation between these two variables (F = 17.96, p-value = 1.04 x 10-14).

#### Prescription Medication Use and Sleep Duration & Disorders
Dataframes isolating number of prescription medications were created to create separate groups of respondents who indicated they take 0 (none) medications, one medication or more than one medication ("multiple"). Embedded pie graphs show the distributions of medication use in short, moderate, long and extensive sleep groups. A chi square analysis was performed to determine if the difference in proprotions of medication use between the extensive group of sleepers and the other three groups (who showed similar distributions) was statistically significant. The results showed there was no stastistical significance even though there appeard to be an observed difference in multiple medications taken in extensive sleepers compared to the other three groups (stat = 0.1368, p-value = 0.9339, critical value = 5.99)..

#### Gender and Sleep Duration & Disorders
Gender differences showed no significant statistical variation between the sexes. the gender mean sleep duration again shows weekdays people sleep less than weekends. Females mean vale 7.75 and Males 7.53 on weekday with weekds mean duration being 8.51 Female to males with 8.2. 

#### Race and Sleep Duration & Disorders:
Race had limited patterns when comparing length of average sleep and speaking to a doctor about sleep concerns.  Generally speaking, across all races, fewer participants spoke to their doctor about sleep concerns no matter how much average sleep they got on work days or weekends.  For example, Black respondents slept the least average amount during the week and weekends, 7.4 and 8.2 respectively, but still were less likely to bring up sleep concerns with their doctor than to share sleep concerns with a healthcare professional.  On the other end of the spectrum, the respondents with the most average sleep during the work week were White respondents with 7.8 hours and Mexican-Americans with the most average weekend sleep at 8.8 hours, but neither group were more likely to with their doctors about sleep either.  Mexican-Americans also averaged the most vigorous daily activity and that might contribute to their longer weekend sleep times, and those respondents who were most active were significantly more likely to speak with a doctor about sleep.  This might be because they are injured or sore from exercise and it could impact their ability to get enough deep sleep.  

One potentially interesting visual to note was that respondents who are Asian we more likely to mark themselves as "never" or "rarely" feels tired during the day when they average the same amount of sleep as the other five races that were included in the study.  They averaged just above 1.33 for feeling tired (a 1.0 = Rarely, or 1 time a month and a 2.0 = Sometimes, or 2-4 times a month).  The next racial group was Other Hispanic at almost 1.7. White respondents averaged the most at nearly 2.0.

#### Age and Sleep Duration:
To investigate the potential relationship between age and nightly sleep duration, we binned the respondents' ages (ranging from 16-80yrs) into 7 age groups ("16-20", "20-30", "30-40","40-50", "50-60", "60-70", "70+") and calculated the average sleep hours on weeknights and weekend-nights for each group. After plotting these averages, it was observed that on weeknights, the younger age groups received the most sleep (16-20yo respondents had an average of 8.1 hours a sleep on weeknights) with subsequent groups having less and less sleep until bottoming out at 7.35 hours in the 50-60yo group. However, the average sleep hours then increased again in the oldest two groups, with those in the 70+ age group having an average of 8.07 hours on average--almost as high as the 16-20yo average. On weekends, there was a different trend: the average sleep hours were the highest for 16-20yo again, but average sleep hours for each of the subsequent age groups seemed to steadily decline. In order to test these differences in the groups' mean sleep hours seen on both weeknights and weekend nights, two one-way ANOVAs were conducted. Both tests indicated that there were significant differences in (at least two) of the group means. The ANOVA for weeknights returned an F-statistic of 51.617 (p-value = 6.56e^-63); the weekend-nights ANOVA returned an F-statistic of 74.272 (p-value = 4.66e^-91). Thus, it seems that age plays a role in the amount of sleep individuals get on average. It would be interesting to investigate these differences in a longitudinal study, as it would allow us to see if these patterns are explained by age or by other differences in the cohorts of this sample.     

### Further study of this topic:
In the future, it could be helpful to start to combine these factors and look at the difference, for example, between active, middle-aged Asian respondents compared to active, middle-aged Mexican-American respondents.  Combining factors would create a more holistic view of Americans. It would also be beneficial to obtain and analyze data from a longitudinal study on sleep, as we would be able to make more solid conclusions regarding sleep across the lifespan. Performing more exploratory analysis on variables that showed statistical significance in the primary analysis could yield additional interesting results. 


### Items in Project 1
1. Datasets folder: Inside the folder, there are the original imports from the CDC website, as well as the merged files we used for the main analysis
2. Jupyter Notebook scripts: Each group member created their own script using the base datasets and focused on comparing different elements to sleep
3. Visualization folder: Once data was formatted to meet individual needs, each member created at least one visualization for their work


