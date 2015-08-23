Title: Update your locate database
Date: 2014-08-16 16:15
Modified: 2014-08-16 16:15
Category: Programming
Tags: unix, locate

The `locate` command is great for searching the entire filesystem for files:

	locate my.cnf

Recently created files and directories might not show up, so update the index:

	locate updatedb
	/usr/libexec/locate.updatedb
