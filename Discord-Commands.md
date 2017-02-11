**Each command must start with the prefix defined in config.json.**

Each command will open a menu for you to select the RSS in that channel to modify, except `rssadd` which must have a link after it. Whatever you're trying to customize, if it is a non-URL/number field, you can use tags to add the feed's information. The user must have Manage Channels permission to use the commands.

|Command|User Type|Opens Menu?|Description|
|-------|----------|-----------|----|
|setgame|Bot Controller|No|Change the 'game' the bot is playing. Setting it to `null` will remove the game.|
|stats|Bot Controller|No|Show current total number of users and number of guilds that the bot is in.|
|rsshelp|Guild Manager|No|List all the commands.|
|rssadd|Guild Manager|No|Add feeds for that specific channel.|
|rssremove|Guild Manager|Yes|Remove feeds.|
|rssmessage|Guild Manager|Yes|Set the custom text message of the feed that will be sent.|
|rssembed|Guild Manager|Yes|Enable and set embed properties to be sent in addition to its regular message.|
|rssfilters|Guild Manager|Yes|Add or remove filters for specific categories for a feed.|
|rsstimezone|Guild Manager|No|Add a timezone to be applied for {date} tags in all feeds for the guild. Only useful if customizing.|
|rssroles|Guild Manager|Yes|Set role subscriptions - either global subscriptions that will mention a role every time a new article from a feed is posted, or filtered subscriptions where the role will only be mentioned with its role-specific filters. The role filters are done *after* the feed filters defined from `rssfilters` if they exist.|
|rsstest|Guild Manager|Yes|Print out the properties for that specific RSS feed and its filter status on whether it passed (if filters exist), along with a randomly chosen feed of any age - in the defined message/embed format in config.json. This was to ease the pains of having to wait for an RSS feed to come just to see how it would look once you designed it in the config.|