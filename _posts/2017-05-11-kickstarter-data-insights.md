## Aim of the project
Learn to use html and d3.js to visualise data. Also, I wanted to use R for data analysis.

## Dataset
I found data from Kickstarter.com as I am interested in fundraising. I picked the data collected until the month of March 2017 from [here](https://webrobots.io/kickstarter-datasets/).

## About Kickstarter
It is a place where artists, musicians, filmmakers, designers, and other creators crowdfund their projects. They can create campaigns, give updates to the community and also send out rewards based on pledged amounts.

## Understanding the metrics
The csv folder had 44 csv files. I picked the first one to see how the data looks. Based on the column headers, I made a sketch of the graphs and metrics that I would like to visualise. This enabled me to finalise the kind of visualisations that I would need.

## Metrics that interested me
1. Goal amount
2. Pledged amount (amount raised)
3. Currency conversion to USD
4. Number of backers
5. Number of days the campaign was active
6. Title of the campaign
7. Brief description

## Initial plan
1. A scatter plot of goal amount vs pledged amount
2. A scatter plot of number of backers vs Success Measure. Success Measure = Pledged amount/goal amount
3. Word cloud of the titles
4. Word cloud of description

With the above plan, I first made a scatterplot for the data from the first csv. Once I got this to work, the challenge was to scale this with all the data that I had. (840 MB)

I used R to merge these 44 csv sheets into one. I further made another dataset with just 3 metrics that I needed for the first graph: goal amount, pledged amount, currency conversion rate (static). This helped to perform operations quicker on my computer.

At this point, I wanted to see how many campaigns raised more than what they expected.

Here is the graph:

![alt text](https://raw.githubusercontent.com/UpadhyayBindu/UpadhyayBindu.github.io/master/_posts/images/successmeasure.png)

Next is the scatterplot with pledged vs goal amount. This is how the graph looks:

![alt text](https://raw.githubusercontent.com/UpadhyayBindu/UpadhyayBindu.github.io/master/_posts/images/goalvspledged1.png)

As you can see, there are lot of outliers. I cleaned the data and here are some more images.

### Limiting goal and pledged to 10,000,000 USD

If goal<10000000 & pledged<10000000, then we eliminate 67 campaigns.

![alt text](https://raw.githubusercontent.com/UpadhyayBindu/UpadhyayBindu.github.io/master/_posts/images/goalvspledged2.png)

### Limiting goal and pledged to 1,000,000 USD

![alt text](https://raw.githubusercontent.com/UpadhyayBindu/UpadhyayBindu.github.io/master/_posts/images/goalvspledged3.png)

### Graph of Pledged amount vs Average amount per backer
![alt text](https://raw.githubusercontent.com/UpadhyayBindu/UpadhyayBindu.github.io/master/_posts/images/pledgedvsavgbacker3.png)

#### Limiting pledged amount to 1,000,000 USD and average per backer to 3000 USD:

![alt text](https://raw.githubusercontent.com/UpadhyayBindu/UpadhyayBindu.github.io/master/_posts/images/pledgedvsavgbacker2.png)

## Words used most often in the title text
![alt text](https://raw.githubusercontent.com/UpadhyayBindu/UpadhyayBindu.github.io/master/_posts/images/titletext1.png)

## Words used most often in the blurb text

![alt text](https://raw.githubusercontent.com/UpadhyayBindu/UpadhyayBindu.github.io/master/_posts/images/textblurb1.png)

## Some totals
* Total number of backers = 23,688,868
* Total number of campaigns = 1,73,026
* Campaigns with pledged > goal = 76805
* Campaigns with pledged < goal = 96221
* Campaigns with no pledged amount = 23,557
* Total pledged amount = $1,999,596,042
* Average per backer = $84.4
