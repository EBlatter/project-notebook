# Design notebook for week ending November 23, 2014

## Description

<!--**TODO:** Fill in this part with information about your work this week:
important design decisions, changes to previous decisions, open questions,
exciting milestones, preliminary results, etc. Feel free to include images
(e.g., a sketch of the design or a screenshot of a running program), links to
code, and any other resources that you think will help clearly convey your
design process.-->

This week, I worked on coding up my prototype. I wrote the files for parsing and interpreting, and implemented different pitches and volumes for notes. I also added some more test songs that I have run through makeMusic.py. These can be found in the sample programs folder in the musicMaker folder. The .xls files are the inputs and the .mid files are the outputs. 

Below is a sample of my program running. It shows the parsed intermediate representation of my program in 'call me maybe.xls'. Essentially, it's a list of notes, which currently each has the relative pitch, the word that will later represent the duration of the note, and the note's volume. Rests are shown as ['0', 'None', '0']. The final output is a midi file that translates all of these into actual notes. 

![sample program running](images/nov23.png)

## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**

I need to start implementing the duration of notes and error handling.

**What questions do you have for your critique partners? How can they best help
you?**

It would be nice to get some input on how my sample programs are so far. Does my language seem to work how you would expect at the moment? Does it seem easy to use?

**How much time did you spend on the project this week?**

I spent about 10 hours on my project this week.

## Post-critique summary

Sisi said that I should think about how different things are represented within a note, and advised that it's usually easier to deal with things in the interpreter than the parser. She also suggested I work out how easy it is to get pitches from Excel to match music output. Also, because the designing part of this has taken me longer than expected, I may want to rethink my schedule and goals.


## Post-critique reflection

This week, I need to get started on actually coding things. I would still like my prototype to be able to deal with different pitches, and so this should allow me to be able to start testing and tweaking how the semantics deal with different positions of notes in the spreadsheet.