#Setup
1. Install [Node.js](https://nodejs.org/en/).
2. Clone files into a directory.
3. Use `npm install` in the directory from terminal/command prompt/etc.
4. Create and get a bot token from https://discordapp.com/developers/applications/me.
    * "My Apps" -> "New App" -> Enter "App Name" and optionally add an app icon -> "Create App" -> "Create a Bot User"
5. Copy "Client ID" from that page and [generate an invite link](https://discordapi.com/permissions.html) to invite the bot to your server.
6. Put your bot token and change whatever else you need to in [config.json](https://github.com/synzen/Discord.RSS/wiki/Configuration).
7. Start the bot by `node rssServer.js`.
8. Optionally use the the [forever module](https://www.npmjs.com/package/forever) to automatically restart the bot if it crashes.



#Using Forever

1. `npm install forever -g` in terminal.
    * add `sudo` before npm if you have permission issues.
2. `cd Discord.RSS` assuming your folder is named Discord.RSS
3. `forever start rssServer.js`

###Realtime Tracking
1. Use `forever list` to show the process index, shown as `[#]` to the left.
2. `forever logs # -f` - you'll now be shown a short recent history of the bot logs, and any further

###Complete History of Bot
1. 1. Use `forever list` to show the `logfile` location as `/my/location/.forever/randomLetters.log`.
2. `cat /my/location/.forever/randomLetters.log`. This is not realtime tracking.

###Stopping the Bot
1. Use `forever list` to show the process index, shown as `[#]` to the left.
2. `forever stop #`
