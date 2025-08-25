---
title: Example I
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
<script src="{{< blogdown/postref >}}index_files/leaflet-providers/leaflet-providers_2.0.0.js"></script>
<script src="{{< blogdown/postref >}}index_files/leaflet-providers-plugin/leaflet-providers-plugin.js"></script>
<link href="{{< blogdown/postref >}}index_files/pagedtable/css/pagedtable.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/pagedtable/js/pagedtable.js"></script>
<link href="{{< blogdown/postref >}}index_files/pagedtable/css/pagedtable.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/pagedtable/js/pagedtable.js"></script>

This map shows the accumulated search effort for Primula pauciflora over its historical habitat covering 9 grid cells
in Bellhouse Park:

``` r
prim_agm <- read.csv("Analysis_outputs/Intermediate/Primula pauciflora_accepted_grouped_merged.csv")
prim_historical <- prim_agm %>% dplyr::filter(assigned_community == "PP1")
prim_sf = assign_cell_geometry_sf(prim_historical, galgrid)

pal <- colorNumeric(palette = "viridis", domain = range(c(0, prim_sf$search_effort), na.rm = TRUE))
m <- leaflet(data = prim_sf) %>%
  # Add a Tiles layer to the map
  addProviderTiles("Esri.WorldImagery") %>%
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
<script type="application/json" data-for="htmlwidget-1">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addProviderTiles","args":["Esri.WorldImagery",null,null,{"errorTileUrl":"","noWrap":false,"detectRetina":false}]},{"method":"addPolygons","args":[[[[{"lng":[-123.3121258329,-123.3117168329,-123.3117168329,-123.3121258329,-123.3121258329],"lat":[48.87259604193872,48.87259604193872,48.87286504193872,48.87286504193872,48.87259604193872]}]],[[{"lng":[-123.3117168329,-123.3113078329,-123.3113078329,-123.3117168329,-123.3117168329],"lat":[48.87259604193872,48.87259604193872,48.87286504193872,48.87286504193872,48.87259604193872]}]],[[{"lng":[-123.3113078329,-123.3108988329,-123.3108988329,-123.3113078329,-123.3113078329],"lat":[48.87259604193872,48.87259604193872,48.87286504193872,48.87286504193872,48.87259604193872]}]],[[{"lng":[-123.3125348329,-123.3121258329,-123.3121258329,-123.3125348329,-123.3125348329],"lat":[48.87232704193872,48.87232704193872,48.87259604193872,48.87259604193872,48.87232704193872]}]],[[{"lng":[-123.3121258329,-123.3117168329,-123.3117168329,-123.3121258329,-123.3121258329],"lat":[48.87232704193872,48.87232704193872,48.87259604193872,48.87259604193872,48.87232704193872]}]],[[{"lng":[-123.3117168329,-123.3113078329,-123.3113078329,-123.3117168329,-123.3117168329],"lat":[48.87232704193872,48.87232704193872,48.87259604193872,48.87259604193872,48.87232704193872]}]],[[{"lng":[-123.3113078329,-123.3108988329,-123.3108988329,-123.3113078329,-123.3113078329],"lat":[48.87232704193872,48.87232704193872,48.87259604193872,48.87259604193872,48.87232704193872]}]],[[{"lng":[-123.3108988329,-123.3104898329,-123.3104898329,-123.3108988329,-123.3108988329],"lat":[48.87232704193872,48.87232704193872,48.87259604193872,48.87259604193872,48.87232704193872]}]],[[{"lng":[-123.3121258329,-123.3117168329,-123.3117168329,-123.3121258329,-123.3121258329],"lat":[48.87205804193872,48.87205804193872,48.87232704193872,48.87232704193872,48.87205804193872]}]]],null,null,{"interactive":true,"className":"","stroke":true,"color":"#BDBDC3","weight":1,"opacity":0.5,"fill":true,"fillColor":["#463480","#443C84","#3B518B","#228B8D","#FDE725","#3B518B","#404588","#3D4E8A","#365D8D"],"fillOpacity":0.8,"smoothFactor":1,"noClip":false},null,null,null,{"interactive":false,"permanent":false,"direction":"auto","opacity":1,"offset":[0,0],"textsize":"10px","textOnly":false,"className":"","sticky":true},null]},{"method":"addLegend","args":[{"colors":["#440154 , #440154 0%, #414287 19.44810497613%, #2B758E 38.89620995226%, #20A486 58.34431492839%, #6DCD59 77.79241990452%, #ECE51B 97.24052488065%, #FDE725 "],"labels":["0","1","2","3","4","5"],"na_color":null,"na_label":"NA","opacity":0.8,"position":"topright","type":"numeric","title":"Accumulated Search Effort in ks","extra":{"p_1":0,"p_n":0.9724052488064997},"layerId":null,"className":"info legend","group":null}]}],"limits":{"lat":[48.87205804193872,48.87286504193872],"lng":[-123.3125348329,-123.3104898329]}},"evals":[],"jsHooks":[]}</script>

The table that this plot is generated from is in the AGM (accepted, grouped, merged) format, output by the
data pipeline which aggregates search trace data, grids it into cells and intersects it with habitat polygons. Here is the data covering
the 9 Bellhouse Park cells:

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":["cell_id"],"name":[1],"type":["int"],"align":["right"]},{"label":["effortId"],"name":[2],"type":["chr"],"align":["left"]},{"label":["search_effort"],"name":[3],"type":["dbl"],"align":["right"]},{"label":["fringe_dist"],"name":[4],"type":["dbl"],"align":["right"]},{"label":["assigned_community"],"name":[5],"type":["chr"],"align":["left"]},{"label":["area"],"name":[6],"type":["dbl"],"align":["right"]},{"label":["area_prop"],"name":[7],"type":["dbl"],"align":["right"]}],"data":[{"1":"373277","2":"2022-04-08...","3":"0.7702174","4":"0","5":"PP1","6":"119.9354","7":"0.1332616"},{"1":"373278","2":"2021-04-15...","3":"0.8952186","4":"0","5":"PP1","6":"456.6756","7":"0.5074174"},{"1":"373279","2":"2021-04-15...","3":"1.2665682","4":"0","5":"PP1","6":"393.4646","7":"0.4371829"},{"1":"373979","2":"2020-04-11...","3":"2.4678189","4":"0","5":"PP1","6":"592.6015","7":"0.6584462"},{"1":"373980","2":"2020-04-11...","3":"5.1418892","4":"0","5":"PP1","6":"882.4500","7":"0.9804999"},{"1":"373981","2":"2020-05-19...","3":"1.2633671","4":"0","5":"PP1","6":"894.7453","7":"0.9941614"},{"1":"373982","2":"2020-05-19...","3":"1.0420709","4":"0","5":"PP1","6":"893.5274","7":"0.9928083"},{"1":"373983","2":"2020-05-19...","3":"1.2058804","4":"0","5":"PP1","6":"240.0844","7":"0.2667604"},{"1":"374683","2":"2020-03-21...","3":"1.4940715","4":"0","5":"PP1","6":"361.1144","7":"0.4012382"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

Here is a description of the columns in this table:

| AGM Column         | Description                                                                                                                                                                                                                                                                                                                                                          |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| cell_id            | Numeric cell id, allocated to a grid cell as configured in the project’s [config.R](https://github.com/IMERSS/biodiversity-change-protocol/tree/main/scripts/config.R) file and manipulated by the utilities in [geomUtil.R](https://github.com/IMERSS/biodiversity-change-protocol/tree/main/scripts/geomUtil.R)                                                    |
| effortId           | A string which summarises each of the search efforts contributing to this search cell. This is purely for traceability and is not used by the analysis computing extirpation probability                                                                                                                                                                             |
| search_effort      | Total accumulated search effort for this grid cell measured in ksec by all observers                                                                                                                                                                                                                                                                                 |
| fringe_dist        | The distance of this cell from historical habitat - these values are all 0 above since the cells lie within the historical habitat                                                                                                                                                                                                                                   |
| assigned_community | The historical community to which this cell is assigned. These numbers are taken from row numbers in the historical plant records table after filtering for those with coordinates - for this analysis in [target_plant_records_2024.csv](https://github.com/IMERSS/biodiversity-change-protocol/tree/mainAnalysis_inputs/Occurrences/target_plant_records_2024.csv) |
| area               | Effective area of the grid cell in square metres after intersecting it with valid habitat polygons - for this analysis, a full cell will be approximately 900 sqm                                                                                                                                                                                                    |
| area_prop          | The proportion that the effective grid cell area is of a standard full grid cell - for this analysis, 900 sqm                                                                                                                                                                                                                                                        |

These cell data are passed for computing regional statistics as the second argument to the `analyse_accepted` function in Analyse.R:

    analyse_accepted(thisTarget, accepted_grouped_merged, habitat_to_centres, exp_weight = exp_weight, solow_prob = solow_low)

Here `exp_weight` is the exponential kernel distance weighting parameter and `solow_prob` is the Solow prior probability of sighting.
This produces posterior regional statistics for extirpation in historical habitat as follows:

``` r
target_stats <- read.csv("Analysis_outputs/Intermediate/Primula pauciflora_stats.csv")
target_stats_historical <- target_stats %>% dplyr::filter(Population == "PP1")
paged_table(target_stats_historical)
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":["cells"],"name":[1],"type":["int"],"align":["right"]},{"label":["searched"],"name":[2],"type":["int"],"align":["right"]},{"label":["pops"],"name":[3],"type":["int"],"align":["right"]},{"label":["habitatSearched"],"name":[4],"type":["chr"],"align":["left"]},{"label":["Central"],"name":[5],"type":["chr"],"align":["left"]},{"label":["Low"],"name":[6],"type":["chr"],"align":["left"]},{"label":["High"],"name":[7],"type":["chr"],"align":["left"]},{"label":["alpha"],"name":[8],"type":["dbl"],"align":["right"]},{"label":["beta"],"name":[9],"type":["dbl"],"align":["right"]},{"label":["mu"],"name":[10],"type":["dbl"],"align":["right"]},{"label":["var"],"name":[11],"type":["dbl"],"align":["right"]},{"label":["Population"],"name":[12],"type":["chr"],"align":["left"]},{"label":["target"],"name":[13],"type":["chr"],"align":["left"]},{"label":["prior_ER"],"name":[14],"type":["dbl"],"align":["right"]}],"data":[{"1":"9","2":"9","3":"1","4":"100.0%","5":"95.8%","6":"91.2%","7":"100.0%","8":"1.35","9":"30.98","10":"0.04171371","11":"0.00119949","12":"PP1","13":"Primula pauciflora","14":"0.57"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

These show the computed parameters of the posterior beta distribution for extirpation expressed in two different forms - the standard (alpha, beta) representation and (mu, var) as parameters for the central estimate for sighting probability and its dispersion. Confidence bands are placed for this at \[91.2%, 100.0%\].

Here is this posterior distribution graphed out:

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-5-1.png" width="672" />
