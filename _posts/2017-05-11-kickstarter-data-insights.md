Aim of the project: Use html and d3.js to visualise data. 

Dataset: I picked the dataset for the month of March 2017 from [here](https://webrobots.io/kickstarter-datasets/). 

The csv folder had 44 csv files. I picked the first one to clean and see how the data looks. Based on the column headers, I made a sketch of the graphs and metrics that I would like to visualise. This enabled me to finalise the kind of visualisations that I would need. 

Metrics that interested me:
1. Goal amount
2. Pledged amount (amount raised)
3. Currency conversion to USD
4. Number of backers
5. Number of days the campaign was active 
6. Title of the campaign
7. Brief description

Initial plan: 
1. A scatter plot of goal amount vs pledged amount
2. A scatter plot of number of backers vs Success Measure. Success Measure = Pledged amount/goal amount
3. Word cloud of the titles
4. Word cloud of description

With the above plan, I first made a scatterplot for the data from the first csv. Once I got this to work, the challenge was to scale this with all the data that I had. (840 MB)

I used R to merge these 44 csv sheets into one. I further made another dataset with just 3 metrics that I needed for the first graph: goal amount, pledged amount, currency conversion rate (static). This helped to perform operations quicker on my computer. 

At this point, I wanted to see how many campaigns raised more than what they expected. 

Here is the graph:

![alt text](https://github.com/UpadhyayBindu/Kickstarterdataanalysis/blob/master/successmeasure.png "Success Measure")
