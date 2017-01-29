Everything is organized by guild ID and handled through the folder  `./sources`. Each JSON file is named with their guild ID, and contains that guild's RSS feeds and customizations. The basic information a guild profile must have is `id`, and `sources` where `sources` is the list of feeds along with their customizations.

The bottom is an example of what would be in a guild source file, for example `./sources/guild_id_here.json`. The basic information for each source in a guild profile must be `name`, `channel,`, and `link`. A more comprehensive example is provided in `./sources/guild_id_here.json` (this file will be ignored by the bot on intialization).

```javascript
"name": "My First Guild!",
"id": "1234567890",
"sources": [{
    //feed #1 settings
    "name": "there",
    "link": "http://somewebsite.com/rss/",
    "channel": "website-feeds"
    }, {
    //feed #2 settings
    }, {
    //feed #3 settings
    }]
}
```

An example with customization would be 

```javascript
	"sources": {
		"name": "there",
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