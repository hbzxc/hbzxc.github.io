---
layout: project
type: project
image: images/SmmothieFinderHome.PNG
title: Smoothie Finder
permalink: projects/SmoothieFinder
# All dates must be YYYY-MM-DD format!
date: 2023-07-010
labels:
  - Python
  - Maps
  - Route Finding
summary: I a great smoothie and wanted to find more
---

Here is a link to the program [http://smoothiepls.pythonanywhere.com/](http://smoothiepls.pythonanywhere.com/).

<img class="ui image" src="{{ site.baseurl }}/images/SmoothieFinderHome.PNG">

I had a great smoothie while visting friends from a chain I had nver heard of, Tropical Smoothie cafe.

I wonder why I had never heard of it so I decided to map its locations out and see why I had never come across it.

I scraped their site using beautiful soup to get addresses. I also decided to scrape two other companies; Jamba Juice and  Smoothie King.

Tropical Smoothie Cafe locations: [https://locations.tropicalsmoothiecafe.com/index.html](https://locations.tropicalsmoothiecafe.com/index.html).

Jamba Juice Locations: [https://locations.jamba.com/](https://locations.jamba.com/).

Smoothie King Locations: [https://locations.smoothieking.com/site-map/us/](https://locations.smoothieking.com/site-map/us/).

All the sites look similar. Jamba and Tropical Smoothie cafe even share the same html and have the same naming conventions. They most likely hired the same company to make the sites with a few alterations.
Which was great for me since I didnt have to change any of the code I wrote to extract locations. Unfortunately I did have to mnake some changes to get the data from Smoothie Kings website.

After addresses were extracted I used Bing maps reverse geolocation to get coordinated to pair with each location.

Each coordinate pair is then plotted on a map and clustered by company.
<img class="ui image" src="{{ site.baseurl }}/images/clusterExample.PNG">

To find routes I calculated the closest store locations and chose the shortest straight line route. Then fed the starting location and end location coordinated into Bing maps API to get a driving route to over lay on the map.
<img class="ui image" src="{{ site.baseurl }}/images/driving_route_example.PNG">

Repository is here [https://github.com/hbzxc/Smoothie_finder](https://github.com/hbzxc/Smoothie_finder).


