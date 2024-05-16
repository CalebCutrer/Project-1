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

## Analysis:
In regards to prescription meds and its impact on sleep ....

Gender differences revealed a .... impact on sleep patterns ....

Race had limited patterns when looking at different sleep factors.  Generally speaking, across all races, fewer participants spoke to their doctor about sleep concerns no matter how much average sleep they got on work days or weekends.  One potentially interesting visual to note was that respondents who are Asian we more likely to mark themselves as "never" or "rarely" feels tired during the day when they average the same amount of sleep as the other five races that were included in the study.  

The age and activity among respondents ....

### Further study of this topic:
In the future, it could be helpful to start to combine these factors and look at the difference, for example, between active, middle-aged Asian respondents compared to active, middle-aged Mexican-American respondents.  Combining factors would create a more holistic view of Americans.  


## Items in Project 1
1. Datasets folder: Inside the folder, there are the original imports from the CDC website, as well as the merged files we used for the main analysis
2. Jupyter Notebook scripts: Each group member created their own script using the base datasets and focused on comparing different elements to sleep
3. Images folder: Once data was formatted to meet individual needs, each member created at least one visualization for their work


