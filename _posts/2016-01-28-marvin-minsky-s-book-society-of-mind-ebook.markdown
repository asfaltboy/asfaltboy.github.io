---
published: true
title: Marvin Minsky's book "Society of mind" ebook
layout: post
tags: ["marvin, minsky", "The, Society, of, Mind", AI, Philosophy]
---
I was deeply saddened to hear of Marvin Minsky's passing just this Sunday. Whenever a great man is gone, I am always filled with terrible guilt that I have not paid enough attention to his work and try to compensate quickly by studying up.

Furvuresly scanning [the wikipedia.com entry](https://en.wikipedia.org/wiki/Marvin_Minsky) for one of this books, I came up with ["Society of mind"](http://www.amazon.com/Society-Mind-Marvin-Minsky/dp/0671607405/). The book immediately grabbed my attention, resonating with my own opinions on the inner working of a mind.

<img src="http://t1.gstatic.com/images?q=tbn:ANd9GcSNWAMrN9a2DaYABpd7mR4t9UCLkX3ZdOlVHiy4Y8Jx8YLiCKZk" alt="Book Cover" style="width: 350px;"/>

Unfortunately, the only online version I could find was a [CC licensed HTML formatted version](http://aurellem.org/society-of-mind/), mentioned in [this Reddit post](https://www.reddit.com/r/artificial/comments/1rbl23/marvin_minskys_book_the_society_of_mind_posted/?ref=search_posts).

And so I took on the task of converting the HTML pages to some ebook formats, mainly so I could read it on my kindle.

The technical feat itself was not complex at all; basically, I passed the TOC page to quick & dirty [spideyscrape.py](https://github.com/paultopia/spideyscrape), and then cleaned up the resulting "one page HTML" from any "per-page" headers/footers, fixed up chapter linking and downloaded the images.

For whoever is interested, the [repo of the cleanup is here](https://github.com/asfaltboy/SocietyOfMind-ebook). The books are available in the same repo, [under releases](https://github.com/asfaltboy/SocietyOfMind-ebook/releases).

The actual ebooks were generated from the HTML with the use of [the excellent calibre app](http://calibre-ebook.com/).