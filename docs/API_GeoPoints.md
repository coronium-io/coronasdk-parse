# GeoPoints

!!! info ""
  A __GeoPoint__ is basically a regular [parse.Object](API_Objects) with a specific data structure, and special queries.
  
## Add a location Object
  
```lua
parse.request( parse.Object.create, "Place" )
:set("__type", "GeoPoint"),
:se("latitude", 40.0),
:set("longitude", -30.0)
:response(cb)
```
  
## A GeoPoint Query
  
```lua
parse.request( parse.Object.query, "Place" )
:where({location =
  {
    ["$nearSphere"] =
    {
      ["__type"] = "GeoPoint",
      latitude = 30,
      longitude = -20.0
    }
  }
})
:options( { limit = 10 } )
:response(cb)
```
  
__[Click to Learn more about GeoPoints](https://www.parse.com/docs/rest/guide#geopoints)__
