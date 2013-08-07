Test-RMarkdown
==============

Play with R Markdown

## Gen for Google Map
```R
source('~/R/Test-RMarkdown/regex.R')
log <- readLines("C:/cygwin/tmp/nmea.txt")
GPGGA <- log[grepl('\\$GPGGA', log)]
GPS <- parse.GPGGA(GPGGA)
GPS$latlon <- with(GPS, paste(latitude, longitude, sep=":"))
```

## R with Map
<http://www.molecularecologist.com/2012/09/making-maps-with-r/>

```R
#define our map's range
lat <- c(48,64)
lon <- c(-140,-110)
#tell what point to center on
center = c(mean(lat), mean(lon))
#zoom: 1 = furthest out (entire globe), larger numbers = closer in
zoom <- 5 
terrmap <- GetMap(center=center, zoom=zoom, maptype= "terrain", destfile = "terrain.png")
```

![Map](http://maps.google.com/maps/api/staticmap?center=56,-125&zoom=5&size=640x640&maptype=terrain&format=png32&sensor=true)
