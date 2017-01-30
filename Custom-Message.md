The main message of the feed can be edited in the guild profile as 

```javascript
"sources": {
	"name": "there",
	"link": "http://somewebsite.com/rss/",
	"channel": "website-feeds",
    "message": "My Message here!"
}
```

OR done through Discord with the command `rssmessage`. Whatever you type into Discord will be directly copied into the guild profile "message" property. If directly editing the profile, do NOT hit go to a new line by hitting enter, use `\n` instead.

Regular [Markdown formatting] (https://support.discordapp.com/hc/en-us/articles/210298617-Markdown-Text-101-Chat-Formatting-Bold-Italic-Underline-) is possible wherever Discord allows, and of course tag use is supported.

`"message": "{date}\nA new feed has arrived!\n\n**{title}**\n{description}"`