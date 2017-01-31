The exact process how the RSS process is outlined in rss.js and initializeall.js, but here is a general outline:

##First-Time Startup
BStarting the bot for the first time will create the database, either in the same directory as the server.js for `sqlite3` or for `mysql` in its own directory.

##Adding a Feed 
A table will be created with the name `(channelID)_(number)(metaLink)`, and all the articles of that feed will be inserted into the table as "seen" since they are all old articles. The feed is also added into the guild's profile with `name`, `channel`, and `link`.

##Grabbing Feeds
On each cycle, it will request the feed, look at *every* article link in the feed, cross reference the feed's table in the database and see if the article exists in the feed's table. If not, it will send to Discord.

##Removing a Feed
The feed's table entry and its source will be deleted from its guild profile.

##Restarting
The bot will cross reference all the articles from the fee  link with the stored links in the database, and account for new feeds:

If `sendOldMessages` in config is set to `true`, the new articles will be sent to Discord with respect to its `maxAge` or `defaultMaxAge` in config, then added into the feed's table.

If `sendOldMessages` is set to false, the new articles will just be added into the feed's table.