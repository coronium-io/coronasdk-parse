<style>.codehilite{padding-bottom:6px;}</style>

# Analytics [parse.Analytics]

## .AppOpened

Send an "Application Opened" event to Parse.

```lua
  parse.request( parse.Analytics.AppOpened )
  :data({})
  :response(cb)
```

[rest/guide#analytics-app-open-analytics](https://www.parse.com/docs/rest/guide#analytics-app-open-analytics)

## .event

Send a custom event to Parse. (See the Parse link below to learn more about using custom events.)

```lua
  parse.request( parse.Analytics.event )
  :data({dimensions:{
    priceRange = "1000-1500",
    source = "craigslist",
    dayType = "weekday"
    }
  })
  :response(cb)
```

[rest/guide#analytics-custom-analytics](https://www.parse.com/docs/rest/guide#analytics-custom-analytics)
