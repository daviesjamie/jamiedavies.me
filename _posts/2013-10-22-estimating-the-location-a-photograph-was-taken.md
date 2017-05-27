---
title: 'Estimating the Location a Photograph Was Taken'
date: 2013-10-22
tags: java lucene computer-vision research talks
---

During the summer of 2013, I took an internship with the [Web and Internet Science (WAIS)](http://www.wais.ecs.soton.ac.uk/) research group at the University of Southampton. For that summer, it became my responsibility to create the group's entry for the [Placing Task](http://www.multimediaeval.org/mediaeval2013/placing2013/) that formed part of the [MediaEval multimedia benchmarking initiative](http://www.multimediaeval.org/mediaeval2013/). The University hadn't made any entries to the MediaEval evaluation before, so the pressure was on to create a good first impression!

The main goal of the MediaEval Placing Task was to create a system that could predict the geographical location that an photograph was taken given just the image itself, and also when combined with metadata such as tags and descriptions. To assess how well the different entries for the task performed, each group was supplied with the same set of 262,000 photographs, which they had to provide an estimated location for. The MediaEval organisers had the actual locations for each of these photographs, and so they could determine which system provided the most accurate guesses.

I was lucky enough to be able to get help and guidance from [Jon Hare](http://users.ecs.soton.ac.uk/jsh2/) and [Sina Samangooei](https://twitter.com/sinjax), the genius researchers behind the [OpenIMAJ project](http://openimaj.org/). Together we devised a system that would use a probability density function over the surface of the Earth to determine the location with the highest probability for each photograph, according to a number of features.

{% figure caption:"Matching features provide sets of (lat, long) points which can be seen as samples drawn from a probability density function over the Earth's surface" %}
![Overlaying features]({% include media name='features.png' %})
{% endfigure %}

Flickr provided the participants of this task with a training dataset of approximately 8.5 million images and their metadata, along with their actual locations. After trialling a number of different features extracted from both the images themselves, and their associated metadata, we finally settled on what we believed to be the most useful:

 - **Tags:** Every tag in the query image was associated with the coordinates of the training images that had that tag.
 - **Image features:** We decided to use two very different features extracted from the images themselves. We used product-quantised CEDD features to achieve a low-precision/high-recall feature, and we used LSH-hashed SIFT features to achieve a high-precision/low-recall feature. For both features, the locations of the images from the training set with the most similar features were used.
 - **Location prior:** Just by looking at the locations of the images in the training set, it is possible to build an idea of where in the world photographs are taken the most. This was used as a ground-truth, and contributed to the probabilities for each query image.

## Results

Each team taking part in the Placing Task was allowed to submit up to 5 separate 'runs' to compete with --- that is, each team could use their system to generate locations for the set of 262,000 test images up to 5 times using different configurations.

We submitted 5 runs using different combinations of features. In our optimal run, which used the location prior, tags and LSH-SIFT features, we managed to place **26.17% of the test images within 1km** of where they had actually been taken. This was the best result achieved in any team that entered the competition, and so we won the Placing Task!

At the end of the summer I went to Barcelona and presented our work at the MediaEval 2013 conference in front of all the other participants. Our success was even [featured on the University website](http://www.ecs.soton.ac.uk/news/4373)!

{% figure caption:"MediaEval 2013, in Barcelona" %}
[![MediaEval 2013]({% include media name='mediaeval.jpg' %})](https://www.flickr.com/photos/69524595@N06/15629198291/in/album-72157646648824353/)
{% endfigure %}

---

You can find the slides from my presentation [here](https://github.com/daviesjamie/soton-mediaeval2013/raw/master/presentations/placing.pdf), and a poster giving an overview of our system [here](https://github.com/daviesjamie/soton-mediaeval2013/raw/master/posters/Mediaeval-placing.pdf).

For more detailed information on the system, you can read the working notes paper submitted to MediaEval [here](http://ceur-ws.org/Vol-1043/mediaeval2013_submission_41.pdf), and a longer research paper submitted to ICMR '14 [here](https://eprints.soton.ac.uk/363376/1/125-Hare.pdf).
