Title: Keeping your git fork up-to-date
Date: 2014-09-02 20:42:51 -0600
Modified: 2014-09-02 20:42:51 -0600
Category: Programming
Tags: git

When your fork falls behind, and it will, here's how to quickly sync it up with master.

First, clone your forked repo, if you havent already:

	git clone git@github.com:<fork>/<repo>.git
	cd drush

Then, merge upstream and push to github:

	git remote add upstream git@github.com:<original>/<repo>.git
	git fetch upstream
	git checkout master
	git merge upstream/master
	git push origin master
