# Design notebook for week ending November 16, 2014

## Description

I spent much of this week playing around with different ways to create sound output. I went through many of the libraries and software [here](https://wiki.python.org/moin/PythonInMusic) to see if any of them were useful. Most had some pretty horrible documentation and were difficult to even install. Eventually, I decided that [MIDIUtil](https://code.google.com/p/midiutil/) was the easiest to use for writing MIDI files. It uses a simple syntax so that I don't have to specify much and it's easy to change just the aspects of a note that I need to and add it to a song. My test of this can be seen in the tests folder in the musictest.py file. I also did a bit of research to see if there was anything for parsing syllables in user input. The [Natural Language Toolkit](http://www.nltk.org/index.html) seemed promising, but I did not have time to figure out why it was not installing correctly on my machine. Because of the difficulty I have had with it, I think I will use a simple heuristic about the number of vowels in a cell to determine the duration of a note. It seems like it will be simpler for me to implement, and it will make it simpler for the user to write a program with my DSL.

Because I spent a lot of time messing with different MIDI and WAV writers, I didn't have time to work on actually implementing my language yet. However, I feel like I have a good idea of the design of my language, so I should be ready to start on the intermediate representation and implementing simpler features of my language next week.

## Questions

I need to start working on the IR for my language. My idea for it is that a program will be translated into a list of notes, each of which has a relative pitch, a duration, and a volume. Does this make sense as an IR, or do I need to reconsider things? Also, if anyone knows of libraries for creating music in Python that are better than the ones I've found, I'd be happy to hear about them.

**How much time did you spend on the project this week? If you're working in a
team, how did you share the labor?**

I spent about 9 hours on my project.

## Post-critique summary

My critique partner said that switching to Excel was good, though I should make sure that I still make sure that the user doesn't need to have too much linguistic knowledge to put words in the correct cells. She also provided some other ideas of things to think about when deciding on how input should be done and how to error handle. In class, our group also discussed the possibility of finding ways to break input into phonemes or syllables or have the user do some of that work themself. Another idea is to have the user input the lyrics as normal English and then formatted in Excel so that the program can easily determine what words have extra letters in them.

## Post-critique reflection

The main takeaway is that I have a lot of things to think about for how I want the user to create input, especially with regards to showing how long a note should be held. I should look to see if there is anything out there that can determine where syllable breaks should be and think about how I should specify user input.
