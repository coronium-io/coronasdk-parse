# Parse API Endpoints

The endpoint meta objects are used to provide the url, parameters, etc. for a specific request. It is always the first argument in a `parse.request` call, for example:

```lua
  local req = parse.request( parse.User.login )
```

!!! note
    You can browse detailed information in the [Plugin API](API_Analytics.md) section.

## Objects [parse.Object]

__.get__

__.query__

__.create__

__.update__

__.delete__

## Users [parse.User]

__.login__

__.logout__

__.me__

__.get__

__.query__

__.create__

__.update__

__.delete__

__.link__

__.unlink__

__.requestPasswordReset__

## Sessions [parse.Session]

__.me__

__.get__

__.query__

__.update__

__.delete__

__.logout__

## Roles [parse.Role]

__.get__

__.create__

__.update__

__.delete__

## Files [parse.File]

__.link__

__.delete__

See also [Working with Files](CH5_Usage.md)

## Analytics [parse.Analytics]

__.AppOpened__

__.event__

## Push [parse.Push]

__.send__

## Installations [parse.Installation]

__.get__

__.query__

__.create__

__.update__

__.delete__

## Config [parse.Config]

__.get__

## Cloud [parse.Cloud]

__.call__

__.job__

## Schemas [parse.Schema]

__.getAll__

__.get__

__.create__

__.update__

__.delete__

## Apps [parse.App]

__.getAll__

__.get__

__.create__

__.update__

## Hooks [parse.Hook]

__.getAll__

__.get__

__.create__

__.update__

__.delete__

## Triggers [parse.Trigger]

__.getAll__

__.get__

__.create__

__.update__

__.delete__
