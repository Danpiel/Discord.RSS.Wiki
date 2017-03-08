Filters can be added to control what feeds get sent to Discord. There are four categories for which filters can be applied to: Title, Description, Summary, Author and Tag (AKA categories, set by feed author). 

```javascript
"sources": {
	"name": "there",
	"link": "http://somewebsite.com/rss/",
	"channel": "website-feeds",
    "message": "My Message here!",
      "filters": {
        "Title": ["Title Filter Here!", "another one~"],
        "Description": ["Description Filter!"],
        "Summary": ["Summary Filter Here!"],
        "Author": ["Author Filter!"]
      }
}
```

The filters are essentially "OR" filters. This meaning that if *any* of the words defined in the filters are found in the feed in their respective categories, then it will pass the filter and be sent to Discord.

Any filters starting with tilde (~) will be a broad search where if it's found *anywhere* in the property it will pass (including inside words). Ex: `~here` will be triggered for the word `there`. To add a tilde to the beginning of the world without having it as a broad search, use `\~` to escape the tilde.