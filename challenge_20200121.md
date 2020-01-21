**Category: Linux**

**Difficulty: Easy**


We have a web server with multiple users uploading files. The files in the webtree should 
be owned by the user ‘www-user’ and group ‘www-devs’ and readable by everyone but sometimes get 
written incorrectly.

Write a bash script to find files and directories in ‘/var/www/html’ that are owned by incorrect
 users and change them to the correct user and group. It should also check permissions and ensure 
 files are writeable by the user and group and readable by everyone.

