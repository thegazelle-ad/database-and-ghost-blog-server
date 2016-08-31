# GHOST BLOG AND DATABASE SERVER

## SETUP
### MARIADB
First go here: https://downloads.mariadb.org/mariadb/repositories and follow the instructions to download MariaDB

After you have installed MariaDB create a database within it and source it with the dump located in dumps/ghostDatabase.dump

### GHOST-BLOG
first install node v4.2. If using nvm do:

`nvm install 4.2`

or

`nvm use 4.2`

if you already have it installed.

Then do:

`npm install --production`

within this folder.

When you are done with this open the config.js file in your favourite text editor. Fill out the uppercase variables at the top of the file as fit. For example use the name for the database you just created in MariaDB in the previous step. Example values are currently filled out, change them as appropriate.

You are now ready. Execute the command

`npm start --production`

while still using node v4.2 and the blog will start. Go to BLOG_URL/ghost to setup your account as the owner of the blog (recommended to call this user admin). You may want to filter through the drafts leftover from the old Wordpress and delete the irrelevant ones, but you can now use the ghost blog to write articles, give them tags, and also meta-descriptions that will be the descriptions that show up when articles are searched on from google.
