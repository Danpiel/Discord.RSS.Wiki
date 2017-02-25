I have implemented tags that can be used in custom feeds. I define tags as phrases in the feed's content that are replaced during feed translation from the source to your Discord, which varies from feed to feed and article to article. They are useable in custom messages/embeds wherever.

|Tag|Description|
|-----|-----|
|{title}|Title of the article.|
|{author}|Author of the article.|
|{description}|Definition of "Description" varies from feed to feed.|
|{summary}|Definition of "Summary" varies from feed to feed.|
|{link}|Link to the article.|
|{imageX}|X replaced with a number 1-9. Sometimes feed image(s) are available - they will be shown with rsstest.|
|{date}|The published date of the article. Timezone can be [customized](https://github.com/synzen/Discord.RSS/wiki/Timezone).|


Putting tags such as {title}, {description}, {summary}, {author}, {link}, {imageX}, {date} will add the feed's respective information into the text. This can either be in the main message, or in the embed. 

As a side note, the tags are not actually the feed article's direct properties. They often contain HTML and other unsightly things unfit to be sent as human-readable feeds, thus the bot does some translating to clean up the content. I've done what I can with the translation to make the tags, particularly {summary} and {description}, reflect the actual source if you were to go the feed's link.