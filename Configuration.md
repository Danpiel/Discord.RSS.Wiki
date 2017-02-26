Any configs with an asterisk `*` beside it indicates that it is *required*.

####Definitions:

`Integer` - A whole, positive number.

`Boolean` - Either `true`/`false`, or `1`/`0`.

`String` - Text that must be enclosed with quotes (`"my text"`).

`Array[String]` - A container enclosed by `[` and `]` with multiple strings inside, separated by commas. Example: `["mythinghere", "mysecondthinghere"]`

##Logging

|Config|Type|Description|
|----|----|----|
|`logDates`|Boolean|Show date on every console log.|
|`discordChannelLog`|String|ID of the Discord channel where guild additions/removal notifications will be sent.|
|`sendConnectErrs`|Boolean|Show connection failures to on requests to feed URLs.|

##Bot Settings

|Config|Type|Description|
|----|----|----|
|`token`*|String|Bot token to login.|
|`prefix`*|String|Prefix for [Discord commands](https://github.com/synzen/Discord.RSS/wiki/Discord-Commands)|
|`defaultGame`|String|The game that the bot will show as playing on startup.|
|`controllerIds`|Array[String]|User IDs who have access to Bot Controller commands.|
|`menuColor`|String|The color of the Discord embed menu commands, between 0 and 16777215. Must be an [*integer* color](https://www.shodor.org/stella2java/rgbint.html). Default is `7833753`.|

##Feed Management

|Config|Type|Description|
|----|----|----|
|`sqlType`*|String|See [Database Selection](#database-selection)|
|`databaseName`*|String|Name of database that will be created and used.|
|`enableBackups`|Boolean|See [Backup System](#automatic-backup-system)|

###Database Selection
It can be set to `sqlite3` or `mysql`. sqlite3 should be easier to work with since it doesn't require any credentials, and the database is created in the same directory as server.js. If you are working with a large number of feeds, `mysql` may be the more ideal choice as you may encounter a "database is busy/closed" error while using sqlite3 because it is constantly writing to the database while the bot is on its schedule and sqlite3 cannot have simultaneous connections.

Should you wish to try and use MySQL, it is quite simple. If you already have it installed on your system, `npm install mysql` in the server.js directory, set up your credentials in mysqlCred.json, change the `sqltype` to `mysql` in config.json, and you're done!

If you don't already have MySQL installed on your system, [install it](https://dev.mysql.com/downloads/mysql/) and set up the root account password. Then follow the same steps as above. The bot will handle everything else.

SQLite on the otherhand requires no setup. It will create the database in the same directory as server.js on first startup.

###Automatic Backup System
The automatic backup system will handle the creation and restoration of corrupted guild profiles in the sources folder with the backups found in in sources/backups folder. Manually adding a backup file will also work, given that the file name is the guild's ID. If you manually edit your sources and for some reason do not check your the validity of your JSON configuration through something like JSONLint, do not enable this as it will overwrite your invalid file.

If this is disabled, only warnings will show that it is an invalid guild profile and will not grab any feeds for that particular guild.


##Feed Settings

Config|Type|Description|
|----|----|----|
|`refreshTimeMinutes`|Integer|Check for new feeds regularly at every interval specified in minutes. Default is `15`.|
|`timezone`|String|This is for the {date} tag customization. By default the date will be in UTC if left blank. To add your own timezone, use a timezone from [this list](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) under the TZ column.|
|`timeFormat`|String|Format how {date} is shown. See [details here](http://momentjs.com/docs/#/displaying/format/). Whatever is here, will be inside `.format(<timeFormat>)` Default is `ddd, D MMMM YYYY, h:mm A z`.
|`maxFeeds`|Integer|The maximum amount of feeds each server is allowed to have. Default is `0` (unlimited).|
|`sendOldMessages`|Boolean|Send unseen messages that were not caught during bot downtime after it has restarted - this may result in message spam. Default is `false`.|
|`defaultMaxAge`|Integer|The max aged feed in days that the bot will grab on startup if it unexpectedly stops. Default is 1.|
|`defaultMessage`*|String|If no custom message is defined for a specific feed, this will be the message the feed will fallback to.|
