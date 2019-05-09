---
title: "Developing Data Products Course Project 1"
author: "Dustin Lanning"
date: "May 7, 2019"
output: 
  html_document: 
    fig_caption: yes
    keep_md: yes
---

##Overview

The purpose of the project is to create a web page using R Markdown that features a map created with Leaflet.

The webpage must be hosted on either GitHub Pages, RPubs, or NeoCities.

The webpage must contain the date that the document was created and it must contain a map created with Leaflet.

##Map

Map of West Virginia "cities". Population data was obtained from http://worldpopulationreview.com/states/west-virginia-population/cities/.


```r
suppressWarnings(library(leaflet))
wv_cities<-data.frame(name = c("Charleston", "Morgantown", "Wheeling", "Parkersburg", "Huntington", "Beckley", "Martinsburg"),
pop = c(47293, 31950, 26688, 29689, 46811, 16372, 17828),
lat = c(38.35, 39.64, 40.08, 39.26, 38.41, 37.79, 39.46),
long = c(-81.63, -79.95, -80.7, -81.54, -82.43, -81.18, -77.98))

suppressMessages(wv_cities %>%
    leaflet() %>%
    addTiles() %>%
    addCircles(weight = 1, radius = wv_cities$pop))
```

<!--html_preserve--><div id="htmlwidget-68f1156120222d0ca4c3" style="width:672px;height:480px;" class="leaflet html-widget"></div>
<script type="application/json" data-for="htmlwidget-68f1156120222d0ca4c3">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addTiles","args":["//{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":1,"detectRetina":false,"attribution":"&copy; <a href=\"http://openstreetmap.org\">OpenStreetMap<\/a> contributors, <a href=\"http://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA<\/a>"}]},{"method":"addCircles","args":[[38.35,39.64,40.08,39.26,38.41,37.79,39.46],[-81.63,-79.95,-80.7,-81.54,-82.43,-81.18,-77.98],[47293,31950,26688,29689,46811,16372,17828],null,null,{"interactive":true,"className":"","stroke":true,"color":"#03F","weight":1,"opacity":0.5,"fill":true,"fillColor":"#03F","fillOpacity":0.2},null,null,null,{"interactive":false,"permanent":false,"direction":"auto","opacity":1,"offset":[0,0],"textsize":"10px","textOnly":false,"className":"","sticky":true},null,null]}],"limits":{"lat":[37.79,40.08],"lng":[-82.43,-77.98]}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->
