Title: Non-Blocking MySQL database export for InnoDB tables
Date: 2014-08-17 16:03
Modified: 2014-08-17 16:03
Category: Programming
Tags: unix, mysql

To quickly dump a large InnoDB database to file without locking it up:

	mysqldump --single-transaction --quick -u webuser -h example.com 'dbname' > dbname.sql

This will issue a START TRANSACTION and as long as the following commands are not 
issued before your export completes, you will have a perfect snapshot:

	ALTER TABLE, CREATE TABLE, DROP TABLE, RENAME TABLE, TRUNCATE TABLE

MyISAM or MEMORY tables dumped while using this option may still change state.
