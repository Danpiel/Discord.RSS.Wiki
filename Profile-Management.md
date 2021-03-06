Everytime a new feed is initialized, a table is created in the database. Manually changing the name of a feed will create a new table for that feed, leaving the old one unmanaged and undeleted unless you manually delete it (or change the name back and remove it through Discord). The names are there more for database management than anything.

In general if you don't want trash lying around in your database don't remove manually remove feeds from `sources`. Instead, remove them from Discord with the command `rssremove` as explained in the section below. Deleting the channel or removing the bot from the server will also purge any traces of the guild from the configs and the database.

And **don't manually edit links to a different feed source** on pre-existing feeds. This will in all old articles being sent, which can be hundreds. New feed links *must* go through the initialization process of getting their old articles inserted into its own table in the database.

###Managing the Database

If the database is getting too large, dropping/deleting the database is perfectly fine. The bot will create a new database, just as it did on first startup, and all articles of all feeds of that time will be stored as "seen".

Do not truncate any feed tables - this will lead to all articles of a feed being marked as unseen, and everything will be spammed into Discord on the next cycle.

Dropping feed tables while the bot is running will mark that feed, at least until the bot is restarted (where it will go through initialization again), as a deleted feed and will not grab any feeds. A warning will be shown in this case on every cycle.