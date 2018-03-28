---
title: Simple Features Now on CRAN
author: B Preston
date: '2017-01-03'
categories:
  - Blog
  - R Consortium Project
  - R Language
slug: simple-features-now-on-cran
---

by Edzer Pebesma

Support for handling and analyzing spatial data in R goes back a long way. In 2003, a group of package developers sat together and decided to adopt a shared understanding of how spatial data should be organized in R. This led to the development of the package [sp](https://cran.r-project.org/web/packages/sp/index.html) and its helper packages [rgdal](https://cran.r-project.org/web/packages/rgdal/index.html) and [rgeos](https://cran.r-project.org/web/packages/rgeos/index.html). sp offers simple classes for points, lines, polygons and grids, which may be associated with further properties (attributes), and takes care of coordinate reference systems. The sp package has helped many users and has made it attractive for others to develop new packages that share sp's conventions for organizing spatial data by reusing its classes. Today, approximately 350 packages directly depend on sp and many more are indirectly dependent.

After 2003, the rest of the world has broadly settled on adopting a standard for so-called "features", which can be thought of as "things" in the real world that have a geometry along with other properties. A feature geometry is called simple when it consists of points connected by straight line pieces, and does not intersect itself. [Simple feature access](https://en.wikipedia.org/wiki/Simple_Features) is a [standard](http://www.opengeospatial.org/standards/sfa) for accessing and exchanging spatial data (points, lines, polygons) as well as for operations defined on them that has been adopted widely over the past ten years, not only by spatial databases such as [PostGIS](http://postgis.net/), but also more recent standards such as [GeoJSON](http://geojson.org/). The sp package and supporting packages such as rgdal and rgeos predate this standard, which complicates exchange and handling of simple feature data.

The "[Simple Features for R](https://github.com/edzer/sfr)" project, one of the projects supported by the R Consortium in its first funding round, addresses these problems by implementing simple features as native R data. The resulting package, [sf](https://cran.r-project.org/web/packages/sf/index.html) provides functionality similar to the sp, rgdal for vector data, and rgeos packages together, but for simple features. Instead of S4 classes used by the sp family, it extends R's data.frame directly, adding a list-column for geometries. This makes it easier to manipulate them with other tools that assume all data objects are data.frames, such as dplyr and tidyverse. Package sf links to the [GDAL](http://www.gdal.org/), [PROJ.4](https://github.com/OSGeo/proj.4/wiki) and [GEOS](https://trac.osgeo.org/geos/) libraries, three major geospatial "swiss army knives" for respectively input/output, cartographic (re)projections, and geometric operations (e.g. unions, buffers, intersections and topological relations). sf can be seen as a successor to sp, rgdal (for vector data), and rgeos.

The simple feature standard describes two encodings: well-known text, a human readable form that looks like "POINT(10 12)" or "LINESTRING(4 0,3 2,5 1)", and well-known binary, a simple binary serialization. The sf package can read and write both. Exchange routines for binary encodings were written in Rcpp, to allow for very fast exchange of data with the linked GDAL and GEOS libraries, but also with other data formats or spatial databases.

The [sf project on GitHub](https://github.com/edzer/sfr) has received a considerable attention. Over 100 issues have been raised, many of which received dozens of valuable contributions, and several projects currently under development ([mapview](https://cran.r-project.org/web/packages/mapview/index.html), [tmap](https://cran.r-project.org/web/packages/tmap/index.html), [stplanr](https://cran.r-project.org/web/packages/stplanr/index.html)) are experimenting with the new data classes. Several authors have provided useful pull requests, and efforts have begun to implement spatial analysis in pipe-based workflows, support dplyr-style verbs and integrate with ggplot.

Besides using data.frames and offering considerably simpler data structures for spatial geometries, advantages of sf over the sp family include: simpler handling of coordinate reference systems (using either EPSG code or PROJ.4 string), the ability to return distance or area values with proper units (meter, feet or US feet), and support for [geosphere](https://cran.r-project.org/web/packages/geosphere/index.html) functions to compute distances or areas for longitude/latitude data, using datum-dependent values for the Earth's radius and flattening.

The sf package is now available from CRAN, both in source form as in binary form for Windows and MacOSX platforms. The authors are grateful to the CRAN team for their strong support in getting the sf package compiled on all platforms. Support from the R Consortium has helped greatly to give this project priority, draw attention in a wider community, and facilitate travel and communication events.

For additional technical information about sf, look [here](http://r-spatial.org/r/2016/11/02/sfcran.html) on my website.
