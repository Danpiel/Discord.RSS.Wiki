"Filtered Subscriptions" are basically global subscriptions, except the mentions only come through if filters set specifically to that role are passed! The same filter categories as feed filters are used. In the guild profile, the role filtered subscriptions are under the property `roleSubscriptions` which is under the feed `filters`.

```js
"sources": [
  {
    "enabled": 1,
    "name": "videostuff",
    "title": "My YouTube Channel",
    "link": "https://www.youtube.com/feeds/videos.xml?channel_id=someID",
    "channel": "youtube-feed",
    "filters": {
      "roleSubscriptions": {
        "roleID": {
          "roleName": "Admin",
          "filters": {
            "Title": ["Filter Here!"]
          }
        },
        "roleID#2": {
          "roleName": "Moderator",
          "filters": {
            "Description": ["another!"],
            "Title": ["something different"]
          }
        }
      }
    }
  }
],
```

Each role is again identified by their ID. If directly editing the config, `roleName` can be omitted since the bot will check the role names and whether they match on startup. 

The filter formatting is the same as feed filters.

**Adding a filtered subscription to a role will remove all of its global subscription, if it exists.**