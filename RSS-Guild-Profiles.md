Everything is organized by guild ID and handled through the folder  `./sources`. Each JSON file is named with their guild ID, and contains that guild's RSS feeds and customizations. The basic information a guild profile must have is `id`, and `sources` where `sources` is the list of feeds along with their customizations.

The bottom is an example of what would be in a guild source file, for example `./sources/guild_id_here.json`. The basic information for each source in a guild profile must be `name`, `channel,`, and `link`. A more comprehensive example is provided in `./sources/guild_id_here.json` (this file will be ignored by the bot on intialization).

```javascript
"name": "My First Guild!",
"id": "1234567890",
"sources": {
  "feed1Name": {
      "link": "http://somewebsite.com/rss/",
      "channel": "website-feeds"
  }, 
  "feed2Name": {
      //feed #2 settings
  }, 
  "feed3Name": {
      //feed #3 settings
  }
}
```

An example with customization would be 

```javascript
	"feedName": {
		"link": "http://somewebsite.com/rss/",
		"channel": "website-feeds",
		"filters": {
			"title": ["important", "key phrase"],
			"description": "stuff"
		},
		"embedMessage": {
			"enabled": 1,
			"properties": {
				"color": 8816239,
				"message": "My embed message is here!"
			}
		},
		"maxAge": 3
	}
```

All customizable feed properties are manageable through Discord, except `maxAge`.

**If directly editing, [check the validity](http://jsonlint.com/) of your edits.**