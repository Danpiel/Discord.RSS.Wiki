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