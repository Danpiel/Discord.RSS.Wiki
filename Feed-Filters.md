Filters can be added to control what feeds get sent to Discord. There are four categories for which filters can be applied to: Title, Description, Summary, and Filter. 

```javascript
"sources": {
	"name": "there",
	"link": "http://somewebsite.com/rss/",
	"channel": "website-feeds",
    "message": "My Message here!",
      "filters": {
        "Title": ["Title Filter Here!"],
        "Description": ["Description Filter!"],
        "Summary": ["Summary Filter Here!"],
        "Author": ["Author Filter!"]
      }
}
```