Title: Converting between formats
Date: 2013-09-26 13:17
Modified: 2013-09-26 13:17
Category: Programming
Tags: mac

There are many tools you can use to convert between file formats.

Convert `bin` to `iso`, with bchunk:

	brew install bchunk
	bchunk input.bin input.cue output.iso

Convert `png` to `svg`, with convert and potrace, for simple images:

	brew install imagemagick potrace
	convert file.png file.pnm
	potrace file.pnm -s -o file.svg -C#ff0000 -k0.6 # red foreground, more detail
	rm file.pnm

More to come!

