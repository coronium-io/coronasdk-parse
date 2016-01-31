# Hooks [parse.Hook]

!!! warning Using Parse-Server?
    __The self-hosted Parse-Server does not support Hooks.__

Please read: __[rest/guide#hooks](https://www.parse.com/docs/rest/guide#hooks)__

## .get

Get a Hook from Parse.

*Parameters:*

* __functionName__

```lua
  parse.request( parse.Hook.get, "functionName" )
  :response(cb)
```

## .getAll

Get all Hooks.

```lua
  parse.request( parse.Hook.getAll )
  :response(cb)
```

## .create

Create a new Hook.

```lua
  parse.request( parse.Hook.create )
  :response(cb)
```

## .update

Update a Hook.

*Parameters:*

* __functionName__

```lua
  parse.request( parse.Hook.update, "functionName" )
  :response(cb)
```

## .delete

Deletes a Hook.

*Parameters:*

* __functionName__

```lua
  parse.request( parse.Hook.delete, "functionName" )
  :response(cb)
```
