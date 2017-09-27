# Sent

sent is a simple plaintext presentation tool.

This is my fork of sent. Sent is developed at http://tools.suckless.org/sent

sent does not need latex, libreoffice or any other fancy file format, it uses
plaintext files and png images. Every paragraph represents a slide in the
presentation.

The presentation is displayed in a simple X11 window. The content of each slide
is automatically scaled to fit the window and centered so you also don't have to
worry about alignment. Instead you can really concentrate on the content.


Requirements:

for Ubuntu, I had to run

- sudo apt install xorg-dev libpng-dev


Demo

To get a little demo, just type

	make && ./sent example

You can navigate with the arrow keys and quit with `q`.


Usage

	sent FILE1 [FILE2 ...]

If one FILE equals `-`, stdin will be read. Produce image slides by prepending a
`@` in front of the filename as a single paragraph. Lines starting with `#` will
be ignored. A `\` at the beginning of the line escapes `@` and `#`. A
presentation file could look like this:

	sent

	@nyan.png

	depends on
	- Xlib
	- libpng

	sent FILENAME
	one slide per paragraph
	# This is a comment and will not be part of the presentation
	\# This and the next line start with backslashes

	\@FILE.png

	thanks / questions?
