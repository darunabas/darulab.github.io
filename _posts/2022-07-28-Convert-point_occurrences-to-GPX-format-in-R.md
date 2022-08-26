---
layout: posts
title: Convert coordinates to GPX format in R
date: 2022-07-28
type: post
published: true
author: paul_markley
status: publish
classes: wide
excerpt_separator: <!--more-->
share: true
header:
  overlay_image: /assets/images/TAMUCC.png
  overlay_filter: 0.2
excerpt: ""
categories:
- Updates
image: /assets/images/TAMUCC.png
tags:
  - link
  - Post Formats
---

## Convert dataframe of coordinates to GPX format in four steps

<hr>

Often, one may have a data frame of locations with attributes such as species
names and may wish to create a GPX file from this data to use with a navigation software such as a GPS device. This can be achieved in four steps as follows:

#### Step 1: Load R library and dataframe
```r
library(terra)

x <- data.frame(NAME=c("Species1", "Species2", "Species3"),
                LAT=c(70.11, 70.032145, 68.619535),
                LON=c(-148.52, -148.640821, -149.556137))
head(x)
```

#### Step 2: Create a spatial vector from the dataframe

```r
v <- vect(x, geom=c("LON", "LAT"), crs="+proj=longlat +datum=WGS84")
```

#### Step 3: Write the spatial vector to file in GPX format

```r
writeVector(v, "~/GPS_wapoints.gpx", filetype="GPX", layer="waypoints", 
            overwrite=TRUE, options="GPX_USE_EXTENSIONS=yes")
```

#### Step 4: Upload file to GPS device
Connect your GPS device to a computer, and drag and drop the new file in the GPX folder of your GPS device. That's it!


