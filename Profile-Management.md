I don't advise tampering with the `name` of feeds. Everytime a new feed is initialized, a table is created in the database. Manually changing the name of a feed will create a new table for that feed, leaving the old one unmanaged and undeleted unless you manually delete it (or change the name back and remove it through Discord). The names are there more for database management than anything.

In general if you don't want trash lying around in your database don't remove manually remove feeds from `sources`. Instead, remove them from Discord with the command `rssremove` as explained in the section below. Deleting the channel or removing the bot from the server will also purge any traces of the guild from the configs and the database.