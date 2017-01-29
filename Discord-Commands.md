Each command must start with the prefix defined in config.json (literally the first line, set to default as `~`).

Each command will open a menu for you to select the RSS in that channel to modify, except `rssadd` which must have a link after it. Whatever you're trying to customize, if it is a non-URL/number field, you can use [tags](#tags) to add the feed's information. The user must have Manage Channels permission to use the commands.

[`rsshelp`]: List the commands to use for Discord.RSS

[`rssadd`]: Add feeds for that specific channel. `(prefix)rssadd rss_link_here`. A new entry will be made in config.json with its name in the format of channelID_feedLink, and will use the default message formatting unless customized otherwise.

[`rssremove`]: To remove feeds. After menu selection, the feed will automatically be removed from config.json.

[`rssmessage`]: Set the custom text message of the feed that will be sent.

[`rssembed`]: Enable and set embed properties to be sent in addition to its regular message.

[`rssfilters`]: Add or remove filters for specific categories for a feed.

[`rsstimezone`]: Add a timezone to be applied for {date} tags in all feeds for the guild.

[`rssroles`]: Set role subscriptions - either global subscriptions that will mention a role every time a new article from a feed is posted, or filtered subscriptions where the role will only be mentioned with its role-specific filters.

[`rsstest`]: Print out the properties for that specific RSS feed and its filter status on whether it passed (if filters exist), along with a randomly chosen feed of any age - in the defined message/embed format in config.json. This was to ease the pains of having to wait for an RSS feed to come just to see how it would look once you designed it in the config. (The role filters are done *after* the feed filters defined from `rssfilters` if they exist.

This is especially useful when you want to add the feed's title and/or description, but you don't know if they'll turn out undefined. However, if the message is too long (that is, over the 2000 character limit), it will not send.