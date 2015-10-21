<style>.codehilite{padding-bottom:6px;}</style>

# Analytics [parse.Analytics]

## .AppOpened

!!! note "You can mess this up"
    If you are not careful, so be careful.

Send an "Application Opened" event to Parse.

```lua
  parse.request( parse.Analytics.AppOpened )
  :data({})
  :response(cb)
```

## .event

Send a custom event to Parse.

```lua
  parse.request( parse.Analytics.event )
  :response(cb)
  ```
