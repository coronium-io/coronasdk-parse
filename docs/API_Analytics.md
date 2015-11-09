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

Send a custom event to Parse.

```lua
  parse.request( parse.Analytics.event )
  :response(cb)
```

[rest/guide#analytics-custom-analytics](https://www.parse.com/docs/rest/guide#analytics-custom-analytics)
