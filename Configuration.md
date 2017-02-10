(config.json)

#Commands
|Category|Config|Type|Description|
|----|----|----|----|
|`logging`|`logDates`|Boolean|Show date on every console log.|
|`logging`|`discordChannelLog`|String|ID of the Discord channel where guild additions/removal notifications will be sent.|
|`botSettings`|`token`|String|Bot token to login.|
|`botSettings`|`prefix`|String|Prefix for [Discord commands](https://github.com/synzen/Discord.RSS/wiki/Discord-Commands)|
|`botSettings`|`defaultGame`|String|The game that the bot will show as playing on startup.|
|`botSettings`|`controllerIds`|Array[String]|User IDs (must be strings) who have access to Bot Controller commands. ex: ["id1", "id2"]|
|`botSettings`|`menuColor`|Integer|The color of the Discord embed menu commands. Must be in [*integer* format](https://www.shodor.org/stella2java/rgbint.html).|
|`feedManagement`|`sqlType`|String|See [Database Selection](#database-selection)|
|`feedManagement`|`databaseName`|String|Name of database that will be created and used.|
|`feedManagement`|`enableBackups`|Boolean|See [Database Selection](#automatic-backup-system)|
|`feedSettings`|`refreshTimeMinutes`|Integer|Check for new feeds regularly at every interval specified in minutes.|
|`feedSettings`|`Timezone`|String|(Optional) This is for the {date} tag customization. By default the date will be in UTC if left blank. To add your own timezone, use a timezone from [this list](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) under the TZ column.|
|`feedSettings`|`maxFeeds`|Integer|The maximum amount of feeds each server is allowed to have.|
|`feedSettings`|`sendOldMessages`|Boolean|Send unseen messages that were not caught during bot downtime after it has restarted - this may result in message spam.|
|`feedSettings`|`defaultMaxAge`|Integer|The max aged feed in days that the bot will grab on startup if it unexpectedly stops.|
|`feedSettings`|`defaultMessage`|String|If no custom message is defined for a specific feed, this will be the message the feed will fallback to.|

##Database Selection
It can be set to `sqlite3` or `mysql`. sqlite3 should be easier to work with since it doesn't require any credentials, and the database is created in the same directory as server.js. If you are working with a large number of servers, `mysql` may be the more ideal choice as you may encounter a "database is busy/closed" error while using sqlite3 because it is constantly writing to the database while the bot is on its schedule and sqlite3 cannot have simultaneous connections.

Should you wish to try and use MySQL, it is quite simple. If you already have it installed on your system, `npm install mysql` in the server.js directory, set up your credentials in mysqlCred.json, change the `sqltype` to `mysql` in config.json, and you're done!

If you don't already have MySQL installed on your system, [install it](https://dev.mysql.com/downloads/mysql/) and set up the root account password. Then follow the same steps as above. The bot will handle everything else.

SQLite on the otherhand requires no setup. It will create the database in the same directory as server.js on first startup.

##Automatic Backup System
The automatic backup system will handle the creation and restoration of corrupted guild profiles in the sources folder with the backups found in in sources/backups folder. Manually adding a backup file will also work, given that the file name is the guild's ID. If you manually edit your sources and for some reason do not check your the validity of your JSON configuration through something like JSONLint, do not enable this as it will overwrite your invalid file.

If this is disabled, only warnings will show that it is an invalid guild profile and will not grab any feeds for that particular guild.