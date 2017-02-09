# Week 2 Assignment: R Markdown and Leaflet
Wei  
9 February 2017  

## The map of Polimi

This is an R Markdown document using Leaflet to show the map of Politecnico di Milano, which is my current university.

Below you can see the code and the interactive map, which you can click on the logos to see more information for the building in my university.


```r
library(leaflet)

poliIcon <- makeIcon(
  iconUrl = "http://hoc.elet.polimi.it/giovio/Immagini/LogoPoli.gif",
  iconWidth = 200/4, iconHeight = 100/4,
  iconAnchorX = 200/4/2, iconAnchorY = 100/4
)

polidf <- data.frame(
  lat = c(45.478050, 45.479595, 45.478742, 45.477929),
  lng = c(9.227369, 9.227761, 9.232390, 9.234558))

poliSites <- c(
  "<a href='http://www.polimi.it/'>East Baltimore Campus</a>",
  "<a href='http://www.biblio.polimi.it/sedi/biblioteche/biblioteca-centrale-di-architettura/'>Central Library of Architecture</a>",
  "<a href='http://www.deib.polimi.it/eng/home-page'>Dipartimento di Elettronica, Informazione e Bioingegneria</a>",
  "<a href='http://esnpolimi.it/site/'>ESN Politecnico Milano</a>"
)

polidf %>% 
  leaflet() %>%
  addTiles() %>%
  addMarkers(icon = poliIcon, popup = poliSites)
```

<!--html_preserve--><div id="htmlwidget-2be3f45d1fa9e9ac3a56" style="width:672px;height:480px;" class="leaflet html-widget"></div>
<script type="application/json" data-for="htmlwidget-2be3f45d1fa9e9ac3a56">{"x":{"calls":[{"method":"addTiles","args":["http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"maxNativeZoom":null,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"continuousWorld":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":null,"unloadInvisibleTiles":null,"updateWhenIdle":null,"detectRetina":false,"reuseTiles":false,"attribution":"&copy; <a href=\"http://openstreetmap.org\">OpenStreetMap\u003c/a> contributors, <a href=\"http://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA\u003c/a>"}]},{"method":"addMarkers","args":[[45.47805,45.479595,45.478742,45.477929],[9.227369,9.227761,9.23239,9.234558],{"iconUrl":{"data":"http://hoc.elet.polimi.it/giovio/Immagini/LogoPoli.gif","index":0},"iconWidth":50,"iconHeight":25,"iconAnchorX":25,"iconAnchorY":25},null,null,{"clickable":true,"draggable":false,"keyboard":true,"title":"","alt":"","zIndexOffset":0,"opacity":1,"riseOnHover":false,"riseOffset":250},["<a href='http://www.polimi.it/'>East Baltimore Campus\u003c/a>","<a href='http://www.biblio.polimi.it/sedi/biblioteche/biblioteca-centrale-di-architettura/'>Central Library of Architecture\u003c/a>","<a href='http://www.deib.polimi.it/eng/home-page'>Dipartimento di Elettronica, Informazione e Bioingegneria\u003c/a>","<a href='http://esnpolimi.it/site/'>ESN Politecnico Milano\u003c/a>"],null,null]}],"limits":{"lat":[45.477929,45.479595],"lng":[9.227369,9.234558]}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->
