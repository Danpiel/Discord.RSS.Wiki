For each guild profile a property "Timezone" can be set, as is shown below in the config. It can be directly added, or added through `rsstimezone` command. **It must be a valid timezone from https://en.wikipedia.org/wiki/List_of_tz_database_time_zones under the TZ column.** Invalid timezones will not resolve and will default back to the timezone set in config.json, or if it is not defined there then it will be UTC.

```javascript
"sources": {
	"name": "there",
	"link": "http://somewebsite.com/rss/",
	"channel": "website-feeds",
    "message": "{date}\nMy Message here!"
    "timezone": "UTC"
}
```

It will change the timezone of the {date} for that guild. This is only useful if they actually use the {date} tag.