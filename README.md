# Car Free Cycle Grid for the UK

The map attempts to show surfaced (i.e. non-muddy) cycle routes that do not require interacting with traffic.

## Why?

- To help spot possible routes that might be suitable for children or cyclists who do not want to interact with traffic.
- To find a place to live that has access to a useful car-free cycle network
- To identify possible improvements to the local network that could open up access


## What will the routes be like?

The routes include separate paved cycle paths, canal towpaths, surfaced bridleways, river paths, ferry crossings and shared use footpaths.

## How should I use it

The map data is not good enough to plan a route without first testing it in person.

Scroll around the map in the area you want to find routes for, and look for possible places to cycle to. Then walk or bike the route in person to check that it works in practice.

## What about including a route planner?

There is little point in having a route planner at this stage, as most of the routes have gaps and/or don't go anywhere.

## I found something wrong with one of the routes

Please [report an issue](https://github.com/samoli/cyclegriduk)

## How was it created?

It uses [OpenStreetMap](https://www.openstreetmap.org/) filtered with a query tool called [Overpass Turbo](https://overpass-turbo.eu). I looked at the areas I know well, and worked on the query until it consistenly included routes that I'd be happy to cycle with children in the context of daily life – for example to or from school. That's why muddy fields that technically have cycle access have not been included – they might be fine in summer but impossible to cross in winter.

The data is addded to a map using [MapBox](https://www.mapbox.com). It was the easiest way to get something up and running, but if you have better ideas, [make a suggestion](https://github.com/samoli/cyclegriduk)

## Overpass Query

The Overpass query used to filter the ways can be found in the [query.txt](query.txt) file. It is roughly the following:

```
type:way
  and (
    (bicycle != no and bicycle != dismount) or highway:cycleway
  )
  and (
    motor_vehicle=no or highway=cycleway or
      (highway=bridleway and surface=asphalt)
  )
```


