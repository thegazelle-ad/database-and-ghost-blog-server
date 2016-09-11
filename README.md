# GHOST BLOG AND DATABASE SERVER

## SETUP
### MARIADB
First go here: https://downloads.mariadb.org/mariadb/repositories and follow the instructions to download MariaDB if you are using Linux. If you are not using Linux you should easily be able to Google how to download it for your operating system. If you are only setting up for development and not for deployment you can also use MySQL which is also 100% compatible.

After you have installed MariaDB you should download the latest database dump from the Gazelle Engineering Google Drive located here:

https://drive.google.com/drive/u/1/folders/0B5ceCeOuBd1tVWNSX2k2RVUtOFk

If you do not have access request it from the lead developers who will give it to you if you are part of the development team.

The dumps will be in the folder "Database Dumps/Timestamped Ghost Dumps".

When you have MariaDB installed you have to create a database and source it with the dump you just downloaded. If you are unfamiliar with MySQL syntax here is an example of doing this from console:

`
mysql -u root -ppassword
create database the_gazelle;
use the_gazelle;
source myDump.dump;
`

Where the text after -p is the password you have set for the database (could also be empty) and what I wrote after source is the path to the dump you downloaded from the directory you initiated the mysql command in.

You should now have a fully functioning MariaDB up and running.

### GHOST-BLOG
first install node v4.2. If using nvm do:

`nvm install 4.2`

or

`nvm use 4.2`

if you already have it installed.

Then do:

`npm install --production`

within this folder.

When you are done with this copy the config.example.js file to a new file config.js as such if using bash:

`cp config.example.js config.js`

Now open the config.js file in your favourite text editor. Fill out the uppercase variables at the top of the file suitably. For example use the name for the database you just created in MariaDB in the previous step. Example values are currently filled out, change them as appropriate.

You are now ready. Execute the command

`npm start --production`

while still using node v4.2 and the blog will start. The admin logins will be the same as on editor.thegazelle.org, but if you're just using this for development you shouldn't need one either as that's all through the Ghost API. If you need access ask the Lead Developer for a login.

If you're setting up for production the blog should now be live, and you can use it to write articles, give them tags, and also meta-descriptions that will be the descriptions that show up when articles are searched on from google and teasers on the website itself.

If you're using it for development you can now setup the config in https://github.com/thegazelle-ad/gazelle-front-end to start developing.
