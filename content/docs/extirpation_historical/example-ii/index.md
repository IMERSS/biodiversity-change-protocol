---
title: Example II
description: ''
date: 2025-06-04
weight: 6
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
<script src="{{< blogdown/postref >}}index_files/leaflet-providers/leaflet-providers_2.0.0.js"></script>
<script src="{{< blogdown/postref >}}index_files/leaflet-providers-plugin/leaflet-providers-plugin.js"></script>
<link href="{{< blogdown/postref >}}index_files/pagedtable/css/pagedtable.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/pagedtable/js/pagedtable.js"></script>
<link href="{{< blogdown/postref >}}index_files/pagedtable/css/pagedtable.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/pagedtable/js/pagedtable.js"></script>

This map shows the accumulated search effort for Crassula connata over its historical habitat covering 10 grid cells
in Bellhouse Park:

``` r
cracon_agm <- read.csv("Analysis_outputs/Intermediate/Crassula connata_accepted_grouped_merged.csv")
cracon_historical <- cracon_agm %>% dplyr::filter(assigned_community == 44)
cracon_sf = assign_cell_geometry_sf(cracon_historical, galgrid)

pal <- colorNumeric(palette = "viridis", domain = range(c(0, cracon_sf$search_effort), na.rm = TRUE))
m <- leaflet(data = cracon_sf) %>%
  # Add a Tiles layer to the map
  addProviderTiles("Esri.WorldImagery") %>%
  # Add the grid layer to the map
  addPolygons(fillColor = ~pal(search_effort), fillOpacity = 0.8, 
              color = "#BDBDC3", weight = 1) %>%
  # Add a legend
  addLegend(pal = pal, values = c(0, max(cracon_sf$search_effort, na.rm = TRUE)),
            opacity = 0.8, title = "Accumulated Search Effort in ks")

# Print the map
m
```

<div class="leaflet html-widget html-fill-item" id="htmlwidget-1" style="width:672px;height:480px;"></div>
<script type="application/json" data-for="htmlwidget-1">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addProviderTiles","args":["Esri.WorldImagery",null,null,{"errorTileUrl":"","noWrap":false,"detectRetina":false}]},{"method":"addPolygons","args":[[[[{"lng":[-123.3117168329,-123.3113078329,-123.3113078329,-123.3117168329,-123.3117168329],"lat":[48.87178904193872,48.87178904193872,48.87205804193872,48.87205804193872,48.87178904193872]}]],[[{"lng":[-123.3113078329,-123.3108988329,-123.3108988329,-123.3113078329,-123.3113078329],"lat":[48.87178904193872,48.87178904193872,48.87205804193872,48.87205804193872,48.87178904193872]}]],[[{"lng":[-123.3108988329,-123.3104898329,-123.3104898329,-123.3108988329,-123.3108988329],"lat":[48.87178904193872,48.87178904193872,48.87205804193872,48.87205804193872,48.87178904193872]}]],[[{"lng":[-123.3117168329,-123.3113078329,-123.3113078329,-123.3117168329,-123.3117168329],"lat":[48.87152004193872,48.87152004193872,48.87178904193873,48.87178904193873,48.87152004193872]}]],[[{"lng":[-123.3113078329,-123.3108988329,-123.3108988329,-123.3113078329,-123.3113078329],"lat":[48.87152004193872,48.87152004193872,48.87178904193873,48.87178904193873,48.87152004193872]}]],[[{"lng":[-123.3108988329,-123.3104898329,-123.3104898329,-123.3108988329,-123.3108988329],"lat":[48.87152004193872,48.87152004193872,48.87178904193873,48.87178904193873,48.87152004193872]}]],[[{"lng":[-123.3121258329,-123.3117168329,-123.3117168329,-123.3121258329,-123.3121258329],"lat":[48.87125104193872,48.87125104193872,48.87152004193872,48.87152004193872,48.87125104193872]}]],[[{"lng":[-123.3117168329,-123.3113078329,-123.3113078329,-123.3117168329,-123.3117168329],"lat":[48.87125104193872,48.87125104193872,48.87152004193872,48.87152004193872,48.87125104193872]}]],[[{"lng":[-123.3113078329,-123.3108988329,-123.3108988329,-123.3113078329,-123.3113078329],"lat":[48.87125104193872,48.87125104193872,48.87152004193872,48.87152004193872,48.87125104193872]}]],[[{"lng":[-123.3108988329,-123.3104898329,-123.3104898329,-123.3108988329,-123.3108988329],"lat":[48.87125104193872,48.87125104193872,48.87152004193872,48.87152004193872,48.87125104193872]}]]],null,null,{"interactive":true,"className":"","stroke":true,"color":"#BDBDC3","weight":1,"opacity":0.5,"fill":true,"fillColor":["#424186","#453681","#25858E","#2A788E","#26828E","#FDE725","#471366","#481B6D","#482576","#481E6F"],"fillOpacity":0.8,"smoothFactor":1,"noClip":false},null,null,null,{"interactive":false,"permanent":false,"direction":"auto","opacity":1,"offset":[0,0],"textsize":"10px","textOnly":false,"className":"","sticky":true},null]},{"method":"addLegend","args":[{"colors":["#440154 , #440154 0%, #433E85 17.8794706251409%, #2E6E8E 35.7589412502818%, #1F998A 53.6384118754227%, #4BC16D 71.5178825005636%, #B8DE29 89.3973531257045%, #FDE725 "],"labels":["0","1","2","3","4","5"],"na_color":null,"na_label":"NA","opacity":0.8,"position":"topright","type":"numeric","title":"Accumulated Search Effort in ks","extra":{"p_1":0,"p_n":0.8939735312570448},"layerId":null,"className":"info legend","group":null}]}],"limits":{"lat":[48.87125104193872,48.87205804193872],"lng":[-123.3121258329,-123.3104898329]}},"evals":[],"jsHooks":[]}</script>

The table that this plot is generated from is in the AGM (accepted, grouped, merged) format, output by the
data pipeline which aggregates search trace data, grids it into cells and intersects it with habitat polygons. Here is the data covering
the 6 Bellhouse Park cells:

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":["cell_id"],"name":[1],"type":["int"],"align":["right"]},{"label":["effortId"],"name":[2],"type":["chr"],"align":["left"]},{"label":["search_effort"],"name":[3],"type":["dbl"],"align":["right"]},{"label":["fringe_dist"],"name":[4],"type":["dbl"],"align":["right"]},{"label":["assigned_community"],"name":[5],"type":["int"],"align":["right"]},{"label":["area"],"name":[6],"type":["dbl"],"align":["right"]},{"label":["area_prop"],"name":[7],"type":["dbl"],"align":["right"]}],"data":[{"1":"375387","2":"2020-03-21...","3":"1.0673861","4":"0","5":"44","6":"0.01422043","7":"1.580047e-05"},{"1":"375388","2":"2020-03-21...","3":"0.8644450","4":"0","5":"44","6":"414.78041422","7":"4.608671e-01"},{"1":"375389","2":"2020-04-11...","3":"2.5542617","4":"0","5":"44","6":"208.08590129","7":"2.312066e-01"},{"1":"376090","2":"2020-03-21...","3":"2.2428481","4":"0","5":"44","6":"748.90675444","7":"8.321186e-01"},{"1":"376091","2":"2022-04-08...","3":"2.4618125","4":"0","5":"44","6":"894.75969483","7":"9.941774e-01"},{"1":"376092","2":"2020-04-11...","3":"5.5930068","4":"0","5":"44","6":"776.01956112","7":"8.622440e-01"},{"1":"376792","2":"2021-04-15...","3":"0.2705882","4":"0","5":"44","6":"325.37158280","7":"3.615240e-01"},{"1":"376793","2":"2020-03-21...","3":"0.4013016","4":"0","5":"44","6":"264.73069849","7":"2.941452e-01"},{"1":"376794","2":"2021-04-15...","3":"0.5743895","4":"0","5":"44","6":"337.82581336","7":"3.753620e-01"},{"1":"376795","2":"2021-04-15...","3":"0.4444706","4":"0","5":"44","6":"201.27199783","7":"2.236356e-01"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

This data format is explained in the [previous example](../example-i)

This produces posterior regional statistics for extirpation in historical habitat as follows:

``` r
target_stats <- read.csv("Analysis_outputs/Intermediate/Crassula connata_stats.csv")
target_stats_historical <- target_stats %>% dplyr::filter(Population == 44)
paged_table(target_stats_historical)
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":["cells"],"name":[1],"type":["int"],"align":["right"]},{"label":["searched"],"name":[2],"type":["int"],"align":["right"]},{"label":["pops"],"name":[3],"type":["dbl"],"align":["right"]},{"label":["habitatSearched"],"name":[4],"type":["chr"],"align":["left"]},{"label":["Central"],"name":[5],"type":["chr"],"align":["left"]},{"label":["Low"],"name":[6],"type":["chr"],"align":["left"]},{"label":["High"],"name":[7],"type":["chr"],"align":["left"]},{"label":["alpha"],"name":[8],"type":["dbl"],"align":["right"]},{"label":["beta"],"name":[9],"type":["dbl"],"align":["right"]},{"label":["mu"],"name":[10],"type":["dbl"],"align":["right"]},{"label":["var"],"name":[11],"type":["dbl"],"align":["right"]},{"label":["Population"],"name":[12],"type":["chr"],"align":["left"]},{"label":["target"],"name":[13],"type":["chr"],"align":["left"]},{"label":["prior_ER"],"name":[14],"type":["dbl"],"align":["right"]}],"data":[{"1":"10","2":"10","3":"1","4":"100.0%","5":"95.6%","6":"90.4%","7":"100.0%","8":"1.17","9":"25.53","10":"0.04377497","11":"0.001511241","12":"44","13":"Crassula connata","14":"0.59"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

These show the computed parameters of the posterior beta distribution for extirpation expressed in two different forms - the standard (alpha, beta) representation and (mu, var) as parameters for the central estimate for sighting probability and its dispersion. Confidence bands are placed for this at \[90.4%, 100.0%\].

Here is this posterior distribution graphed out:

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-5-1.png" width="672" />
