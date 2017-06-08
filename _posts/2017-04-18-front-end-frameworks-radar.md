## Brief
Visualise a technology radar for front-end frameworks

## Team
Bindu Upadhyay, Daniel Mariano, Farzaneh Akhbar

## Learning goals
* Present a story by using data
* Learn to extract data by using some APIs

## What is a technology radar?

Every six months or so, ThoughtWorks publishes its Technology Radar.
>The radar is a document that sets out the changes that we think are currently interesting in software development - things in motion that we think you should pay attention to and consider using in your projects. It reflects the idiosyncratic opinion of a bunch of senior technologists based on our day-to-day work and experiences. While we think this is interesting, it should not be taken as a deep market analysis. "

Here is the radar for languages and frameworks: <https://www.thoughtworks.com/radar/languages-and-frameworks>

## Why a technology radar?
* The inspiration for this was from the example we saw from our professor's site: http://obren.info/tech/

* The number of frameworks are ever increasing. Some of them catch up while others don't get popular. We wanted to see what could be some characteristics of these emerging frameworks.

## Our process

We considered the frameworks from this link: http://usablica.github.io/front-end-frameworks/compare.html

The next step was to collect some data about these frameworks. We collected the following data:

* Twitter: Tweets, likes, followers, following, tweets from last 1 week

* Github: Repository Created on, updated last on, subscribers, forks, stars

* Stackoverflow: Number of questions, count per tag

* Google trends

* YouTube

### Working with data from Twitter

I used the twitter api to get the tweets from the last 1 week for some of the frameworks. This was done using R. After that, I generated a wordcloud to see what were the frequent terms.

### Working with data from Github


## Putting it all together

The tech radar that we designed has 4 quadrants. The x axis is for.. and the y axis is for ..
Based on this, we named the quadrants by using the same terms that are used in the standard radar.
* Adopt: represents blips that we think you should be using now. We don't say that you should use these for every project; any tool should only be used in an appropriate context. However we do think that a blip in the adopt ring represents something where there is no doubt that it's proven and mature for use.
* Trial Ring is for blips that we think are ready for use, but not as completely proven as those in the adopt ring. So for most organizations we think you should use these on a trial basis, to decide whether they should be part of your toolkit. Typically we are happy to use trial blips now, but we realize that most readers will be more cautious than us.
* Assess Ring are things that you should look at closely, but not necessarily trial yet - unless you think they would be a particularly good fit for you. Typically blips in the assess ring are things that we are currently trialling, on our projects.
* Hold Ring is for things that are getting attention in the industry, but we don't think are ready for use. Sometimes this is because we don't think they are mature enough yet, sometimes it means we think they are irredeemably flawed. We don't have an "avoid" ring, but we do throw things in the hold ring that we wish our clients wouldn't use.

We placed some example frameworks in each of these quadrants. This could be explored further by having a formula
