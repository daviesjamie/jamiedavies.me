---
title: 'Graphically Exploring Fractals'
date: 2012-04-21
tags: projects java
---

*Fractal Explorer* was created for the first of two coursework assignments for
an "advanced programming" module I took in my first year at university. The
task was to create a Java application that could be used to interactively view
and explore a visual representation of the [Mandelbrot
Set](http://en.wikipedia.org/wiki/Mandelbrot_set) and some corresponding [Julia
Sets](http://en.wikipedia.org/wiki/Julia_set).

{% figure caption:"A zoomed in view of the Mandelbrot Set (left), with a Julia
Set corresponding to a chosen point (right)."
%} ![Fractal Explorer]({% include media name='fractal.png'%})
{% endfigure %}

This coursework was great fun, and I regard it as one of the most enjoyable
courseworks I completed at university. I found implementing the algorithms
rather addictive. So much so, that I ended up getting a bit carried away and
spent probably far too much time adding a slew of extra features, including:

- Click-and-drag zooming, with animations
- Live real-time preview of the Julia Set associated with the point underneath
  the cursor
- Full multi-threaded rendering of the fractals
- Ability to customise the fractal calculations, including the maximum number
  of iterations to use, and smoothing the results to blend colours together
  more smoothly
- Exporting of the fractals at custom sizes (making for some
  [pretty]({% include media name='fractal-wallpaper.png' %})
  [wallpapers]({% include media name='fractal-wallpaper2.png' %}))
- Display of other fractal algorithms, including the [Burning
  Ship](http://en.wikipedia.org/wiki/Burning_ship_fractal)
- And perhaps the most ~~important~~ *unnecessary* feature: full control over
  the hues and colours used for the fractals

* * *

*Fractal Explorer* is available as a JAR executable
[here]({% include media name='fractal.jar' %}).

I plan to one day rewrite this in a different language, such as Python, Ruby or
even using Javascript to draw on to a HTML 5 canvas. I've had those plans for
a number of years though, so don't hold your breath...

