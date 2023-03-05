+++
title = "A Map: Housing Market in Ireland"
description = "A cool map I made + learning to use GeoJSON"
date = "2023-02-27"
author = "Leon Reilly"
categories = [
    "Notes"
   
]
tags = [
    "Housing",

]
toc = false
draft = false

+++

## Preface

Anything with in the "Notes" category will be usually short and captures my thoughts. They're not as rigorous as my other posts.


## Cool Map


<iframe title="2022 Median House Prices in Ireland" aria-label="Map" id="datawrapper-chart-j8EK7" src="https://datawrapper.dwcdn.net/j8EK7/4/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="833" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();
</script>


For some reason, the Central Statistics Office (CSO) doesn't publish a map like this, so I decided to do it myself. It was a <abbr title="real pain in the ass">pretty good</abbr> exercise in both research and learning how to manipulate GeoJSON and CSO data. 

A few observations about this map:
* As we approach Dublin, Cork, or Galway, house prices increase. This pattern is most obvious around Dublin. Sadly, this is probably not due to the numinous beauty of Dublin. It just suggests that the areas adjacent to Dublin are where many commute to work.
* Ballyboughal (A41) is an outlier, relative to the areas surrounding it. From looking at the data more closely, only 9 houses were sold in this area in 2022. For whatever reason, the houses just happened to be quite expensive, i.e., above the €700,000 mark. The median price for Ballyboughal is usually closer to ~€500,000. Regardless, in 2022, Ballyboughal's median house price was the highest in the country. 
* For comparison, the average house price in each area is very similar to the median house price. 

## Making the Map

For what is supposed to be public data, finding the boundaries for each Eircode in Ireland was unnecessarily cumbersome. Here it is, in GeoJSON format, so nobody else has to search for it.
* <a href="/resources/Eircode_Map.json" download>Eircode Map: Full Detail GeoJSON</a> 
* <a href="/resources/Eircode_Map.json" download>Eircode Map: Simplified GeoJSON</a>


