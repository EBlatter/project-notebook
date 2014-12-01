# Design notebook for week ending November 30, 2014

## Description

<!--**TODO:** Fill in this part with information about your work this week:
important design decisions, changes to previous decisions, open questions,
exciting milestones, preliminary results, etc. Feel free to include images
(e.g., a sketch of the design or a screenshot of a running program), links to
code, and any other resources that you think will help clearly convey your
design process.-->
Most of this week was spent enjoying Thanksgiving with my family. However, I did manage to add a bit of instruction for how to use the program in its current state, so hopefully that should make it easier for other people to try it for themselves and give feedback. These changes can be found in the README for my project.

## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**

I need to start implementing duration of notes. The current plan is to use simple heuristics about the number of consecutive vowels in a word, but I'll need to see how easy that is to implement. Once I finish that, I need to get some error checking in and make sure it's easy to use.

**What questions do you have for your critique partners? How can they best help
you?**

It would be great if they could try to create some songs with my language. They need to keep in mind that duration of notes is not yet implemented.

**How much time did you spend on the project this week? If you're working in a
team, how did you share the labor?**

2.5 hours

## Post-critique summary
Sisi said my sample programs produce output she would expect so far. She also had some questions and suggestions about how to make input easiest for users.


## Post-critique reflection
I need to do some tests with users. Most of my sample programs have been created with the help of sheet music as reference so I could write them quickly, so I need to see how difficult it is to create it from scratch. I also need to see how easy it is for people who are less experienced with music to create the sounds they want. I also need to implement duration of notes because it's significant in creating songs that sound correct.
