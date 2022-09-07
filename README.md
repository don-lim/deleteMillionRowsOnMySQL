# deleteMillionRowsOnMySQL

Deleting rows actually take longer time than inserting rows. Deleting millions of rows of data on an active server with many concurrent users is not easy.

If you have an active server with many users, call this procedure so that your server will breath after deleting every 10000 records.

createProcedureForDeleteMillionRowsWithPause.sql

