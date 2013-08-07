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
