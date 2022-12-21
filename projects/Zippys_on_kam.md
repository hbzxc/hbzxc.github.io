---
layout: project
type: project
image: images/Zippys_on_Kam.PNG
title: Zippys on Kam 
permalink: projects/Zippys_on_Kam
# All dates must be YYYY-MM-DD format!
date: 2022-12-16
labels:
  - Python
  - Plotly Dash
  - Bing Maps API
  - Beautiful Soup
summary: I made a program that will scrape the Zippys website to get restaurant locations and then route you to the nearest Zippys on Kamehameha hwy.
---

I made this program in two days instead of studying for a final.

Is it useful? Not really and it only works with locations on Oahu. 

There are currently no air travel directions just driving instructions.

Why did I make this? I thought it would be funny.

<img class="ui image" src="{{ site.baseurl }}/images/Zippys_on_Kam.PNG">

This program was created using python, beautiful soup to scrape websites, plotly to visualize the data, and Bing maps get the geographic coordinates from the restaurant addresses.

Try it out: [https://zippys_on_kam-hblazier.pythonanywhere.com/](https://zippys_on_kam-hblazier.pythonanywhere.com/)

How it works:

The program first scrapes the [Zippys](https://www.zippys.com/) website for a list of locations. 
It will then check each location to get an address, check if it is open, and record a list of service provided at each location.

Then these address are geocoded using Bing maps to get a coordinate.

Bing maps is also used to get directions between two sets of coordinates, provided a distance, drive time and traffic estimate.

The resulting coordinates are plotted and everything is mapped using plotly and mapbox.

no address given:
<img class="ui image" src="{{ site.baseurl }}/images/Kam_Zip_none.PNG">

Address given but no route found
<img class="ui image" src="{{ site.baseurl }}/images/Kam_Zip_vaddress.PNG">

Address given and route found
<img class="ui image" src="{{ site.baseurl }}/images/Kam_Zip_valid.PNG">

Close up of map
<img class="ui image" src="{{ site.baseurl }}/images/Kam_Zip_Close.PNG">

Code: [https://github.com/hbzxc/Zippys-on-Kam](https://github.com/hbzxc/Zippys-on-Kam)


