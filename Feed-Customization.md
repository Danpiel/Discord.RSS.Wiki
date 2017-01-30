I have implemented tags that can be used in custom feeds. I define tags as phrases in the feed's content that are replaced during feed translation from the source to your Discord, which varies from feed to feed and article to article. They are useable in custom messages/embeds wherever.

|Tag|Description|
|-----|-----|
|{title}|Title of the article.|
|{author}|Author of the article.|
|{description}|Definition of "Description" varies from feed to feed.|
|{summary}|Definition of "Summary" varies from feed to feed.|
|{link}|Link to the article.|
|{image}|Sometimes a feed image is available.|
|{date}|The published date of the article. Timezone can be [customized](https://github.com/synzen/Discord.RSS/wiki/Timezone).|


Putting tags such as {title}, {description}, {summary}, {author}, {link}, {image}, {date} will add the feed's respective information into the text. This can either be in the main message, or in the embed. 