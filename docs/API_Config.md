# Config [parse.Config]

!!! warning "Using Parse-Server?"
    __The self-hosted Parse-Server does not support the Config module.__

## .get

Get the Parse application Config.

```lua
  parse.request( parse.Config.get )
  :response(cb)
```

[rest/guide#config](https://www.parse.com/docs/rest/guide#config)
