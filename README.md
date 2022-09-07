# Delete Million Rows On MySQL

Deleting rows actually take longer time than inserting rows. Deleting millions of rows of data on an active server with many concurrent users is not an easy task. You may paralyze the server for a long time effectively shutting down the service if you use a regular delete command.

- Running the following sql command will create an event that will delete one million rows every 5 minutes. Make sure you enable the event scheduler from PHPMyAdmin or a terminal globally after logged in as the main user of MySQL. `SET GLOBAL event_scheduler = ON;` Most default settings automatically turn off the event scheduler when you reboot the system. So, you need to turn on the event scheduler every time you reboot.

createEventForDeleteMillionRowsSimpleLoop.sql

- If you have an active server with many users, call this procedure so that your server will breath after deleting every 10000 records. You can use this even for pages for regular users if you expect a large number of rows to delete.

createProcedureForDeleteMillionRowsWithPause.sql

* You shouldn't use `WHERE id = "12345"` if the id is an integer. It will waste time in finding both strings and integer if you use double quotes. Be sure to include `ORDER BY id` because it will shorten the transaction time. 
