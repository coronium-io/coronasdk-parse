# Push [parse.Push]

!!! warning "Using Parse-Server?"
    __The self-hosted Parse-Server does not support the Push module.__

Please read: __[rest/guide#push-notifications](https://www.parse.com/docs/rest/guide#push-notifications)__

## .send

Send a Push request.

```lua
  parse.request( parse.Push.send )
  :response(cb)
```
