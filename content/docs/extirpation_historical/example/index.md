---
title: Example
description: ''
date: 2025-06-04
weight: 5
---

<link href="{{< blogdown/postref >}}index_files/htmltools-fill/fill.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/htmlwidgets/htmlwidgets.js"></script>
<script src="{{< blogdown/postref >}}index_files/jquery/jquery-3.6.0.min.js"></script>
<link href="{{< blogdown/postref >}}index_files/leaflet/leaflet.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/leaflet/leaflet.js"></script>
<link href="{{< blogdown/postref >}}index_files/leafletfix/leafletfix.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/proj4/proj4.min.js"></script>
<script src="{{< blogdown/postref >}}index_files/Proj4Leaflet/proj4leaflet.js"></script>
<link href="{{< blogdown/postref >}}index_files/rstudio_leaflet/rstudio_leaflet.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/leaflet-binding/leaflet.js"></script>

This map shows the accumulated search effort for Primula pauciflora over its historical habitat covering 9 grid cells
in Bellhouse Park:

``` r
prim_agm <- read.csv("Analysis_outputs/Intermediate/Primula pauciflora_accepted_grouped_merged.csv")
prim_historical <- prim_agm %>% dplyr::filter(assigned_community == 77)
prim_sf = assign_cell_geometry_sf(prim_historical, galgrid)

pal <- colorNumeric(palette = "viridis", domain = range(c(0, prim_sf$search_effort), na.rm = TRUE))
m <- leaflet(data = prim_sf) %>%
  # Add a Tiles layer to the map
  addTiles() %>%
  # Add the grid layer to the map
  addPolygons(fillColor = ~pal(search_effort), fillOpacity = 0.8, 
              color = "#BDBDC3", weight = 1) %>%
  # Add a legend
  addLegend(pal = pal, values = c(0, max(prim_sf$search_effort, na.rm = TRUE)),
            opacity = 0.8, title = "Accumulated Search Effort in ks")

# Print the map
m
```

<div class="leaflet html-widget html-fill-item" id="htmlwidget-1" style="width:672px;height:480px;"></div>
<script type="application/json" data-for="htmlwidget-1">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addTiles","args":["https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":1,"detectRetina":false,"attribution":"&copy; <a href=\"https://openstreetmap.org/copyright/\">OpenStreetMap<\/a>,  <a href=\"https://opendatacommons.org/licenses/odbl/\">ODbL<\/a>"}]},{"method":"addPolygons","args":[[[[{"lng":[-123.3121258329,-123.3117168329,-123.3117168329,-123.3121258329,-123.3121258329],"lat":[48.87259604193872,48.87259604193872,48.87286504193872,48.87286504193872,48.87259604193872]}]],[[{"lng":[-123.3117168329,-123.3113078329,-123.3113078329,-123.3117168329,-123.3117168329],"lat":[48.87259604193872,48.87259604193872,48.87286504193872,48.87286504193872,48.87259604193872]}]],[[{"lng":[-123.3113078329,-123.3108988329,-123.3108988329,-123.3113078329,-123.3113078329],"lat":[48.87259604193872,48.87259604193872,48.87286504193872,48.87286504193872,48.87259604193872]}]],[[{"lng":[-123.3125348329,-123.3121258329,-123.3121258329,-123.3125348329,-123.3125348329],"lat":[48.87232704193872,48.87232704193872,48.87259604193872,48.87259604193872,48.87232704193872]}]],[[{"lng":[-123.3121258329,-123.3117168329,-123.3117168329,-123.3121258329,-123.3121258329],"lat":[48.87232704193872,48.87232704193872,48.87259604193872,48.87259604193872,48.87232704193872]}]],[[{"lng":[-123.3117168329,-123.3113078329,-123.3113078329,-123.3117168329,-123.3117168329],"lat":[48.87232704193872,48.87232704193872,48.87259604193872,48.87259604193872,48.87232704193872]}]],[[{"lng":[-123.3113078329,-123.3108988329,-123.3108988329,-123.3113078329,-123.3113078329],"lat":[48.87232704193872,48.87232704193872,48.87259604193872,48.87259604193872,48.87232704193872]}]],[[{"lng":[-123.3108988329,-123.3104898329,-123.3104898329,-123.3108988329,-123.3108988329],"lat":[48.87232704193872,48.87232704193872,48.87259604193872,48.87259604193872,48.87232704193872]}]],[[{"lng":[-123.3121258329,-123.3117168329,-123.3117168329,-123.3121258329,-123.3121258329],"lat":[48.87205804193872,48.87205804193872,48.87232704193872,48.87232704193872,48.87205804193872]}]]],null,null,{"interactive":true,"className":"","stroke":true,"color":"#BDBDC3","weight":1,"opacity":0.5,"fill":true,"fillColor":["#463480","#443C84","#3B518B","#228B8D","#FDE725","#3B518B","#404588","#3D4E8A","#365D8D"],"fillOpacity":0.8,"smoothFactor":1,"noClip":false},null,null,null,{"interactive":false,"permanent":false,"direction":"auto","opacity":1,"offset":[0,0],"textsize":"10px","textOnly":false,"className":"","sticky":true},null]},{"method":"addLegend","args":[{"colors":["#440154 , #440154 0%, #414287 19.44810497613%, #2B758E 38.89620995226%, #20A486 58.34431492839%, #6DCD59 77.79241990452%, #ECE51B 97.24052488065%, #FDE725 "],"labels":["0","1","2","3","4","5"],"na_color":null,"na_label":"NA","opacity":0.8,"position":"topright","type":"numeric","title":"Accumulated Search Effort in ks","extra":{"p_1":0,"p_n":0.9724052488064997},"layerId":null,"className":"info legend","group":null}]}],"limits":{"lat":[48.87205804193872,48.87286504193872],"lng":[-123.3125348329,-123.3104898329]}},"evals":[],"jsHooks":[]}</script>
