Title: Clear the DNS Cache
Date: 2014-09-04 12:55:27 -0600
Modified: 2014-09-04 12:55:27 -0600
Category: Programming
Tags: mac, dns

You've updated `/etc/hosts` and your changes aren't reflected in Google Chrome.  Try clearing the DNS cache.

## Chrome

Navigate to `chrome://net-internals/#dns` and click "Clear Host Cache"  
Navigate to `chrome://net-internals/#sockets` and click "Flush Socket Pools"

## Mac OS X v10.6

	sudo dscacheutil -flushcache

## Mac OS X v10.7+

	sudo killall -HUP mDNSResponder
