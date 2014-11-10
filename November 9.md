# Design notebook for week ending November 9, 2014

## Description

Because of the problems with rtf files, I decided to use excel files instead. This also seems like it would be easier for the user to edit their song too, especially the pitches. It would also be easier for me to allow the user to create two lines of melody at once with this new format, if I choose to do so in the future. I fiddled with some potential libraries I could use to help with things. I'll be using xlrd to read in and extract info from excel files. I also have figured out how to extract information about the font from it and where the words are in the file. I also looked into some other libraries, like the sound libraries used in the CS 5 sound lab and PyPEG, which Sisi recommended for parsing in Python.

## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**

I need to decide on an AST, though I think this should be fairly straightforward. I also need to think about what sort of errors I will need to deal with for error-handling.

**What questions do you have for your critique partners? How can they best help
you?**
Is the current design of my language intuitive/does it make sense? What sort of errors would you expect it to produce?

**How much time did you spend on the project this week? If you're working in a
team, how did you share the labor?**
I spent 8 hours on the project.

## Post-critique summary

PyPEG might be a useful parser if I want to use Python. I also need to think about possible problems with using rtf files as input - not all editors format them the same way and using subscripts/superscripts could be difficult. Also, I should think about my AST. My project is very design-focused. Finally, my late-night assumption that the major due dates were every week was incorrect.

## Post-critique reflection

I need to rethink how I'm doing input. After opening my sample programs in a couple of other editors that can open rtf files, I saw that in everything except TextEdit, the formatting got messed up, especially for the subscripts and superscripts. Using the sub/superscripts was also not the easiest experience.