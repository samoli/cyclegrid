# Car Free Cycle Grid for the UK

The map attempts to show surfaced cycle routes that do not require interacting with traffic.

<img src="https://raw.githubusercontent.com/samoli/cyclegrid/master/preview.png" width="240" />

[View the map](https://www.cyclegrid.co.uk)

## Why?

- To help discovery of pleasant cycle routes in your area that minimise traffic interaction
- To find a place to live that has proximity to a useful car-free cycle network
- To identify possible improvements to the local network that could connect it to useful routes

## What will the routes be like?

The routes include separate paved cycle paths, canal towpaths, surfaced bridleways, river paths, ferry crossings and shared use footpaths.

## How should I use it

Scroll around the map in the area you want to find routes for, and look for possible routes. Then walk or bike the route in person to check that it works in practice. **The map data is not reliable enough to plan a route without first testing it in person.**

## What about including a route planner?

There is little point in having a route planner at this stage, as most of the routes have gaps and/or don't go anywhere.

## I found something wrong with one of the routes

If a suitable route is missing, or if an inappropriate route is incuded, please [report an issue](https://github.com/samoli/cyclegrid)

## A grid you say?

Well no, it’s nothing like a grid, even if you use the on-road cycleways. But maybe visualising what we have will help encourage improvements to the network.

## How was it created?

It uses [OpenStreetMap](https://www.openstreetmap.org/) data filtered with a query tool called [Overpass Turbo](https://overpass-turbo.eu). I looked at the areas I know well, and worked on the query until it consistenly included routes that I'd be happy to cycle with children in the context of daily life – for example to or from school. That's why muddy fields that technically have cycle access have not been included – they might be fine in summer but impractical or impossible to cross in winter.

The data is addded to a map using [MapBox](https://www.mapbox.com). It was the easiest way to get something up and running, but if you have better ideas, [make a suggestion](https://github.com/samoli/cyclegriduk)

## Overpass Query

The Overpass query used to filter the ways can be found in the [query.txt](query.txt) file. It is roughly the following:

```
type:way and ((bicycle!=no and bicycle!=dismount) or highway:cycleway) and (motor_vehicle=no or highway=cycleway or (highway=bridleway and (surface=asphalt or surface=compacted or surface=concrete or surface=paved)) or (highway=footway and (bicycle=permissive or bicycle=yes)))
```

