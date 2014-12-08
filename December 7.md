# Design notebook for week ending December 7, 2014

## Description

<!-- **TODO:** Fill in this part with information about your work this week:
important design decisions, changes to previous decisions, open questions,
exciting milestones, preliminary results, etc. Feel free to include images
(e.g., a sketch of the design or a screenshot of a running program), links to
code, and any other resources that you think will help clearly convey your
design process. -->
This week, I changed how I parsed my language. I switched from using pyparsing to pyPEG. Though I was able to get pyparsing to work well enough for earlier features, it was a bit hacked in and would have been difficult to use for figuring out the length of notes. I likely would have ended up just passing the text directly to semantics and figured out the note lengths entirely there. PyPEG has built-in functions that make parsing a lot simpler; I was able to use some fairly straight-forward regexes to pull out a list of each group of consecutive vowels in a cell. Semantics can then figure out how to turn those vowels into a value for note duration. Also, with pyPEG, I actually have an AST, which makes the code a lot nicer and neater.

Passing all of the vowel groups to semantics has been a good design choice because it makes it easier to change how duration of note is calculated. My first idea was to use some sort of heuristics to determine the length of note, where each group of consecutive vowels in a word would count as a note. However, separating a note into subnotes within it like that didn't seem to make sense for the structure of the language. Also, there were a lot of problems dealing with things like silent vowels. My sample programs which had been working fine before kept getting extra notes in it, and I quickly realized that it was due to silent vowels. Considering I have essentially zero experience with natural language processing and linguistics, I had trouble coming up with a simple heuristic that would deal with this well and couldn't figure out how to catch the many cases where this would come up in. Therefore, I decided that each column would represent one note, and then the length of the longest string of a repeated vowel within it would be the duration of the note.

Current problems with finding note length:
* Words with 2 vowels normally are turned into longer notes (books, cheese, etc.)
* Consonants that can be where the music is (the MMMBop problem)
* Putting each sound in its own square might not be as intuitive, less freedom for user

Advantages over old solution:
* Doesn't have to deal with silent vowels
* Puts more responsibility/trust in users and thus simplifies my code

I also ran a couple of small informal user tests, which can be seen in MusicMaker/sampleprograms in the aarthi files and frosh files. The different sets of users seemed to agree that it was difficult to create a song with how they would expect it to sound. However, they found it fun and said that the output made sense. It seemed like it was similar to figuring out how to play a song by randomly pressing keys on a piano. I tried doing it myself, too. In MusicMaker/sampleprograms/someone_like_you, I started out using sheet music to write out Adele's "Someone Like You" and then later switched to doing it by ear. It is clear that the second half sounds absolutely nothing like the song, while the first half sounds fine.

Previous critiques suggested that I color the rows to distinguish different notes. I've added a template that colors the rows to make it easier to tell the difference between rows, which can be seen in MusicMaker.xlt. Each row of the same color is an octave away from the previous one of that color. Though a user doesn't have to use this, it might be helpful.

I also added some error checking. If a note has no vowels or is too low, an error will be thrown. Also, a warning will be thrown if a user puts in more than one note in a column. Though it may be possible for me to play these simultaneously, in the user test/code review in class I was told that it wasn't really necessary and wasn't something they really expected, though they also didn't expect it to break the program. This is why I chose to just throw a warning. However, some of the people I user tested with this week said it was a feature they would like, so I may reevaluate this decision next week, though it may require some refactoring.


## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**

I need to make sure everything works in a way that other people expect. I also need to make sure I'm checking errors properly.

**What questions do you have for your critique partners? How can they best help
you?**

What errors should I be catching? Though it may be difficult to use, does the output my language creates make sense based on what you input (especially note duration)?

**How much time did you spend on the project this week? If you're working in a
team, how did you share the labor?**

9 hours

## Post-critique summary
Sisi said that it with the way it's currently set up, it may be difficult to create notes with the right length. It's also difficult for her to create songs without having the sheet music as reference, despite having some musical knowledge.


## Post-critique reflection
I still need to work on how I'm going to do lengths of notes. I also want to test on a few more users and see how hard it is and if there's anything I can do to make it easier.