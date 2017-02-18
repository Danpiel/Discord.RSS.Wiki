**Each command must start with the prefix defined in config.json.**

Each command will open a menu for you to select the RSS in that channel to modify, except `rssadd` which must have a link after it. Whatever you're trying to customize, if it is a non-URL/number field, you can use tags to add the feed's information. The user must have Manage Channels permission to use the commands.

If *Input Type* is specified, it will prompt the user for input after the command is used. If none is specified, then the command is used as `<prefix><command> <whatever>`

##Bot Controller Commands

Bot controllers are specified through the config via IDs. See config for details

|Command|Input Type|Description|
|-------|----------|-----------|----|
|setgame||Change the 'game' the bot is playing. Setting it to `null` will remove the game.|
|stats||Show current total number of users and number of guilds that the bot is in.|

##Guild Manager Commands

For anyone with "Manage Channel" permission in each guild.

|Command|Input Type|Description|
|-------|-----------|----|
|rsshelp||List all the commands.|
|rssadd||Add feeds for that specific channel.|
|rssremove|Menu|Remove feeds.|
|rssmessage|Menu|Set the custom text message of the feed that will be sent.|
|rssembed|Menu|Enable and set embed properties to be sent in addition to its regular message.|
|rssfilters|Menu|Add or remove filters for specific categories for a feed.|
|rsstimezone||Add a timezone to be applied for `{date}` tags in all feeds for the guild. Only useful if customizing.|
|rssroles|Menu|Set role subscriptions - either global subscriptions that will mention a role every time a new article from a feed is posted, or filtered subscriptions where the role will only be mentioned with its role-specific filters. The role filters are done *after* the feed filters defined from `rssfilters` if they exist.|
|rsstest|Menu|Print out the properties for that specific RSS feed and its filter status on whether it passed (if filters exist), along with a randomly chosen feed of any age - in the defined message/embed format in config.json. This was to ease the pains of having to wait for an RSS feed to come just to see how it would look once you designed it in the config.|

##User Commands

Usable by anyone in guild.

|Command|Input Type|Description|
|-------|-----------|----|
|subme|Role Name|Enabled/disabled by "Manage Roles" permission. Shows a list of feeds with their roles* that can be added to the user, then add that role to the user.
|unsubme|Role Name|Enabled/disabled by "Manage Roles" permission. Shows a list of feeds with their respective roles that can be removed from the user, then remove that role from the user.
\*Roles that are *beneath* the bot's role order, and are subscribed to feeds.

\*\*Roles that are *beneath* the bot's role order.