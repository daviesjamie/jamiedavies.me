---
title: 'Crosswords and a Cup of Java'
date: 2012-05-12
tags: projects java
---

I've mentioned it [before]({{ site.baseurl }}{% post_url 2012-04-21-graphically-exploring-fractals %}), but the "advanced programming" module I took in my first year at the University of Southampton was one of my favourites.

The task for the second coursework in this module was to create a Java application that could be used to interactively complete a crossword, similar to the [Guardian's web-based crossword application](https://www.theguardian.com/crosswords).

*Crossworder* was my submission for this coursework.

{% figure caption:"*Crossworder* in action." %}
![Crossworder]({% include media name='crossworder.png' %})
{% endfigure %}

As is my wont, I got a bit excited whilst implementing the coursework guidelines and added a bunch of extra features, including:

- Keyboard navigation around the crossword using the arrow keys
- Clicking on a clue in one of the lists highlights the matching row/column in the crossword, and moves the cursor to the starting letter
- Loading and saving of crosswords from/to XML files, using a custom-designed schema (also saving any progress made in the puzzle as well)
- Dynamic resizing of the crossword grid, depending on the size of the loaded puzzle and the size of the window
- Displaying a log of details such as when and who completed a clue, as well as whether any solutions are correct or not --- which I creatively dubbed "solved clue support"

* * *

You can download *Crossworder* as a JAR executable [here]({% include media name='crossworder.jar' %}).

Unfortunately having an interface with which to create a crossword puzzle wasn't in the coursework specification, so you'll just have to make do with the two bundled example crossword puzzles. Oops.
