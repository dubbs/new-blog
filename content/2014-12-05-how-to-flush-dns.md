Title: How to Flush DNS
Date: 2014-12-05 10:59:20 -0600
Modified: 2014-12-05 10:59:20 -0600
Category: Programming
Tags: linux, mac

## WinXP

Start > Run > `cmd`

    ipconfig /flushdns

## Win7

Start > Search programs and files > `cmd` > Right click > Run as administrator

	ipconfig /flushdns

## Win8

Start Screen > `cmd` > Right click > Run as administrator

	ipconfig /flushdns

## IPhone

Simply toggle "Airplane Mode"

## MAC OS X 10.7+

    sudo killall -HUP mDNSResponder

## MAC OS X 10.6

    sudo dscacheutil -flushcache

## MAC OS X 10.5.1

	sudo lookupd -flushcache

## Linux

	sudo /etc/init.d/nscd restart


