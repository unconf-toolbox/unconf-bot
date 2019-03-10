# unconf-bot <img src="https://raw.githubusercontent.com/unconf-toolbox/unconf-website/master/figs/logo.png" align="right" width="120" />


Follow the steps below to create a Twitter bot that retweets tweets with your unconference's hashtag! Note: you will need access to a server that can run a job. These instructions work for Linux servers. For Windows, see [this post](https://medium.com/@randerson112358/create-a-twitter-bot-using-r-5a94f1b1b886). 

### Step 1: Create a Twitter account for your unconf 

You'll need a phone number and an email to do this. 

### Step 2: Create a Twitter developer account for your unconf's Twitter account

[developers.twitter.com](https://developer.twitter.com)

You have to answer some questions about what you will be using your developer account for. Confirm with email before moving onto the next step. 

### Step 3: Create a Twitter app in your new developer account

[Twitter apps](https://developer.twitter.com/en/apps) 

You'll have to answer more questions and agree to Twitter's policies. 

### Step 4: Clone this repo 

This repo contains all the files necessary to Tweet from R! Thanks [@ellisp](https://github.com/ellisp)! You'll need the following R packages: 

```
install.packages(c("tweeteR", "stringi", "dplyr", "base64enc")))
devtools::install_github("hadley/emo")
```

### Step 5: Put credentials in the [credentials setup](https://github.com/unconf-toolbox/unconf-bot/blob/master/credentials_setup.R) file

To find these credentials: [Developer twitter](https://developer.twitter.com/en/apps) -> "Details" button next to your app -> Keys and Tokens

### (Optional) Step 5.5: Customize your retweets

Edit [retweetRstats.R](https://github.com/unconf-toolbox/unconf-bot/blob/master/tweeting/retweetRstats.R) to change the comment that get posted with the retweet. (Currently emoji!)

### Step 6: Set up the bot to run on a schedule. (This step is different for Windows.)

Set up a job on a server to run the shell scripts (scripts will also need to be changed if you're on Windows) in the cron-scripts folder. There is a different script for each Twitter task. For example, to run the retweet script every 5 minutes, put 
```
*/5 * * * * ~/unconf-bot/cron_scripts/retweet
```
in the `crontab` file. 

# Credit to Rrobot
A twitterbot that tweets about #rstats

This is the source code for [@HappyRrobot](https://twitter.com/HappyRrobot?lang=en), an inoffensive Twitter bot that tweets 
a few times each day something about R.  Typical tweets are retweets of popular recent posts using the `#rstats` hashtag, 
babble based on classic books about R, and text mining summaries from blogs about R.

Read my [creators' blog post](http://freerangestats.info/blog/2015/12/29/Rrobot-born) about when I was born.
