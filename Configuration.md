#Configuration
(config.json)

1. `token` : Bot token to login through server.js

2. `sqlType`: See [Database Selection](#database-selection)

3. `menuColor` The color of the Discord embed menu commands. Must be in [*integer* format](https://www.shodor.org/stella2java/rgbint.html).

4. `timezone`: (Optional) This is for the {date} tag customization. If left blank, the date will be in UTC. To add your own timezone, use a timezone from [this list](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) under the TZ column.

5. `refreshTimeMinutes`: The bot will check for new feeds regularly at every interval specified in minutes here.

6. `databaseName`: Name of database that will be created.

7. `sendOldMessages`: Send unseen messages that were not caught during bot downtime after it has restarted - this may result in message spam.

8. `defaultMaxAge`: The max aged feed in days that the bot will grab on startup if it unexpectedly stops.

9. `defaultMessage`: If no custom message is defined for a specific feed, this will be the message the feed will fallback to.

10. `maxFeeds`: The maximum amount of feeds each server is allowed to have.

##Database Selection
It can be set to `sqlite3` or `mysql`. sqlite3 should be easier to work with since it doesn't require any credentials, and the database is created in the same directory as server.js. If you are working with a large number of servers, `mysql` may be the more ideal choice as you may encounter a "database is busy/closed" error while using sqlite3 because it is constantly writing to the database while the bot is on its schedule and sqlite3 cannot have simultaneous connections.

Should you wish to try and use MySQL, it is quite simple. If you already have it installed on your system, `npm install mysql` in the server.js directory, set up your credentials in mysqlCred.json, change the `sqltype` to `mysql` in config.json, and you're done!

If you don't already have MySQL installed on your system, [install it](https://dev.mysql.com/downloads/mysql/) and set up the root account password. Then follow the same steps as above. The bot will handle everything else.

SQLite on the otherhand requires no setup. It will create the database in the same directory as server.js on first startup.