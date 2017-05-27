---
title: 'Telehex: A Television Show Tracker'
date: 2014-01-08
tags: projects python javascript django google-app-engine
---

Have you ever used [Teletext](https://en.wikipedia.org/wiki/Teletext)? It used to be a handy way to check news headlines, weather forecasts and television schedules right on your TV, many years before the digital revolution.

[*Telehex*](http://telehex3001.appspot.com) is a web application that gives a modern twist on the Teletext service, allowing users to create their own personalised TV schedule, complete with reminders and recommendations. It also includes a very liberal dosage of hexagon-themed design, as the name suggests (which makes for some fun CSS!).

{% figure caption:"Seriously, look at those hexagons." %}
![The main Telehex search page]({% include media name='search.png' %})
{% endfigure %}

I created it with several of my friends --- [Hayden](https://eskriett.com), [Miles](https://milesarmstrong.co.uk/), [Chantel](https://www.linkedin.com/in/chantel-spencer-bowdage-05945a4a), [Will](https://www.linkedin.com/in/william-buss-b752a176), [Jack](https://www.linkedin.com/in/jack-flann-bb017aa6) and [Simon](https://www.linkedin.com/in/simonbidwell) --- as a group coursework entry for a "scripting languages" module at university.

The specification for the coursework pitted teams of students against each other, in a bid to win a contract from a (sadly, fictional) company. The teams had to create a prototype web application that would run on the [Google App Engine](https://developers.google.com/appengine) to show off their server-side Python and client-side Javascript skills, in no more than 1,500 lines of code.

{% figure caption:"The Telehex page for [New Girl](http://telehex3001.appspot.com/show/new_girl)." %}
![The Telehex page for New Girl]({% include media name='new_girl.png' %})
{% endfigure %}

The main features of Telehex include:

 - Giving detailed and up-to-date information on almost every TV show you can think of, scraped on demand from a number of online sources (such as [The TVDB](http://thetvdb.com/))
 - Allowing users to sign in to the website with a Google account, and subscribe to their favourite TV shows
 - Presenting a profile page to each user, showing their subscribed shows and when they are next airing
 - Allowing users to view the TV shows they've subscribed to on a calendar
 - Sending email updates to users each week, telling them which of their subscribed TV shows are airing in the coming week
 - Showing the ratings for each season and episode of each TV show in an interactive graph, allowing easy discovery of the best (and worst) episodes for the show
 - Providing an explorable network graph of TV shows that are similar to each other, by comparing user subscriptions --- allowing users to find other TV shows they might like

It turned out that our fictional clients loved the concept of Telehex and we were awarded a mark of 92%.

* * *

Telehex is still running at <http://telehex3001.appspot.com>, where it remains almost entirely untouched since it was submitted.

The code for Telehex can be found at <https://github.com/eskriett/telehex>.
