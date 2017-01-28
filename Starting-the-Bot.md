#Setup
1. Install [Node.js](https://nodejs.org/en/).
2. Clone files into a directory.
3. Use `npm install` in the directory from terminal/command prompt/etc.
4. Create and get a bot token from https://discordapp.com/developers/applications/me.
5. Invite your bot to your server with a link generated from https://discordapi.com/permissions.html, putting your bot's client ID there.
6. Put your bot token and change whatever else you need to in [config.json](#configuration)
7. Start the bot by `node server.js` in terminal/command prompt/etc.
8. Add feeds either [via Discord](#discord-commands), or [manually create](#rss-storage) and [customize](#feed-customization) in the sources folder.
9. Optionally use the the [forever module](https://www.npmjs.com/package/forever) to automatically restart the bot if it crashes.


#Using Forever

1. `npm install forever -g` in terminal.
    * add `sudo` before npm if you have permission issues.
2. `cd Discord.RSS` assuming your folder is named Discord.RSS
3. `forever start server.js`

###Realtime Tracking
1. Use `forever list` to show the process index, shown as `[#]` to the left.
2. `forever logs # -f` - you'll now be shown a short recent history of the bot logs.

###Complete History of Bot
1. 1. Use `forever list` to show the `logfile` location as `/my/location/.forever/randomLetters.log`.
2. `cat /my/location/.forever/randomLetters.log`. This is not realtime tracking.

###Stopping the Bot
1. Use `forever list` to show the process index, shown as `[#]` to the left.
2. `forever stop #`