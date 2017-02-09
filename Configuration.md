(config.json)

1. `prefix`: Prefix for [Discord commands](#discord-commands)

2. `token` : Bot token to login through server.js

3. `logDates`: Show the date on every console log.

4. `enableBackups`: Enable automatic backups creation and restoration in sources/backups folder. Manually adding a backup file will also work, given that the file name is the guild's ID. If you manually edit your sources and for some reason do not check your the validity of your JSON configuration through something like [JSONLint](http://jsonlint.com/), do not enable this as it will overwrite your invalid file.

5. `sqlType`: See [Database Selection](#database-selection)

6. `menuColor`: The color of the Discord embed menu commands. Must be in [*integer* format](https://www.shodor.org/stella2java/rgbint.html).

7. `timezone`: (Optional) This is for the {date} tag customization. By default the date will be in UTC if left blank. To add your own timezone, use a timezone from [this list](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) under the TZ column.

8. `refreshTimeMinutes`: The bot will check for new feeds regularly at every interval specified in minutes here.

9. `databaseName`: Name of database that will be created.

10. `sendOldMessages`: Send unseen messages that were not caught during bot downtime after it has restarted - this may result in message spam.

11. `defaultMaxAge`: The max aged feed in days that the bot will grab on startup if it unexpectedly stops.

12. `defaultMessage`: If no custom message is defined for a specific feed, this will be the message the feed will fallback to.

13. `maxFeeds`: The maximum amount of feeds each server is allowed to have.

14. `discordChannelLog`: (Channel ID) Log guild addition/deletion in a Discord channel.

15. `defaultGame`: The game that the bot will show when logged in.

16. `controllerIds`: Array of user IDs who have access to `~setgame` and `~stats`. ex: `[id1, id2]`

##Database Selection
It can be set to `sqlite3` or `mysql`. sqlite3 should be easier to work with since it doesn't require any credentials, and the database is created in the same directory as server.js. If you are working with a large number of servers, `mysql` may be the more ideal choice as you may encounter a "database is busy/closed" error while using sqlite3 because it is constantly writing to the database while the bot is on its schedule and sqlite3 cannot have simultaneous connections.

Should you wish to try and use MySQL, it is quite simple. If you already have it installed on your system, `npm install mysql` in the server.js directory, set up your credentials in mysqlCred.json, change the `sqltype` to `mysql` in config.json, and you're done!

If you don't already have MySQL installed on your system, [install it](https://dev.mysql.com/downloads/mysql/) and set up the root account password. Then follow the same steps as above. The bot will handle everything else.

SQLite on the otherhand requires no setup. It will create the database in the same directory as server.js on first startup.