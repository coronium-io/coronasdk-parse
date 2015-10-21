<style>.codehilite{padding-bottom:6px;}</style>

# Apps [parse.App]

## .get

Get an App.

*Parameters:*

* __applicationId__

```lua
parse.request( parse.App.get, "applicationId" )
:response(cb)
```

## .getAll

Get all Apps.

```lua
parse.request( parse.App.getAll )
:response(cb)
```

## .create

Create a new App.

```lua
parse.request( parse.App.create )
:response(cb)
```

## .update

Update an App.

*Parameters:*

* __applicationId__

```lua
parse.request( parse.App.update, "applicationId" )
:response(cb)
```

## .delete

Deletes an App.

*Parameters:*

* __applicationId__

```lua
parse.request( parse.App.delete, "applicationId" )
:response(cb)
```
