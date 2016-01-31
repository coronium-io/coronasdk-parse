# Triggers [parse.Trigger]

!!! warning Using Parse-Server?
    __The self-hosted Parse-Server does not support Triggers.__

Please read: __[rest/guide#hooks](https://www.parse.com/docs/rest/guide#hooks)__

## .get

Get a Trigger from Parse.

*Parameters:*

* __triggerName__

```lua
  parse.request( parse.Trigger.get, "triggerName" )
  :response(cb)
```

## .getAll

Get all Triggers.

```lua
  parse.request( parse.Trigger.getAll )
  :response(cb)
```

## .create

Create a new Trigger.

```lua
  parse.request( parse.Trigger.create )
  :response(cb)
```

## .update

Update a Trigger.

*Parameters:*

* __triggerName__

```lua
  parse.request( parse.Trigger.update, "triggerName" )
  :response(cb)
```

## .delete

Deletes a Trigger.

*Parameters:*

* __triggerName__

```lua
  parse.request( parse.Trigger.delete, "triggerName" )
  :response(cb)
```
