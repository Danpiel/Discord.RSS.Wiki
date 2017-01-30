I have defined "global subscriptions" as roles that get mentioned on *every* article sent from a feed. Global subscriptions are set as such in config, or set through the command `rssroles`:

```javascript
"sources": {
	"name": "there",
	"link": "http://somewebsite.com/rss/",
	"channel": "website-feeds",
    "message": "My Message here!",
    "roleSubscriptions": ["ID1", "ID2"]
}
```

`roleSubscriptions` must be an array, with the elements being the role ID. This is probably not possible to directly edit the individual roles seeing that there is no easy way to get the role IDs without a bot, thus using `rssroles` is best.

**Adding a global subscription to a role will remove all of its filtered subscriptions, if they exist.**

**For the role mentions to show up on messages, the tag `{subscriptions}` must be used.**