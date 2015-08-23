Title: Ignorning ri and RDoc during gem install
Date: 2014-08-22 11:56
Modified: 2014-08-22 11:56
Category: Programming
Tags: ruby

I personally never use the ri (Ruby Index) and RDoc (Ruby Documentation).

To prevent them from installing during `gem install`, just add this line to your ~/.gemrc or /etc/gemrc:

	gem: --no-rdoc --no-ri
