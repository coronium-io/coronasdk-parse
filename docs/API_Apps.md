<style>.codehilite{padding-bottom:6px;}</style>

# Apps [parse.App]

!!! warning "Using Parse-Server?"
    __The self-hosted Parse-Server does not support the Apps module.__

## .get

Get an App.

*Parameters:*

* __applicationId__

```lua
  parse.request( parse.App.get, "AppId" )
  :header("X-Parse-Email","<PARSE-ACCOUNT-EMAIL>")
  :header("X-Parse-Password","<PARSE-ACCOUNT-PASSWORD>")
  :response(cb)
```

[rest/guide#apps-fetching-apps](https://www.parse.com/docs/rest/guide#apps-fetching-apps)

## .getAll

Get all Apps.

```lua
  parse.request( parse.App.getAll )
  :header("X-Parse-Email","<PARSE-ACCOUNT-EMAIL>")
  :header("X-Parse-Password","<PARSE-ACCOUNT-PASSWORD>")
  :response(cb)
```

[rest/guide#apps-fetching-apps](https://www.parse.com/docs/rest/guide#apps-fetching-apps)

## .create

Create a new App.

```lua
parse.request( parse.App.create )
:header("X-Parse-Email", "<PARSE-ACCOUNT-EMAIL>")
:header("X-Parse-Password", "<PARSE-ACCOUNT-PASSWORD>")
:set("appName", "my new app")
:set("clientClassCreationEnabled", false)
:response(cb)
```

[rest/guide#apps-creating-apps](https://www.parse.com/docs/rest/guide#apps-creating-apps)

## .update

Updates an App.

*Parameters:*

* __applicationId__

```lua
  parse.request( parse.App.update, "AppId" )
  :header("X-Parse-Email", "<PARSE-ACCOUNT-EMAIL>")
  :header("X-Parse-Password", "<PARSE-ACCOUNT-PASSWORD>")
  :set("appName", "updated app name")
  :set("clientClassCreationEnabled", true)
  :response(cb)
```

See the Parse REST link below for more detailed options.

[rest/guide#apps-updating-apps](https://www.parse.com/docs/rest/guide#apps-updating-apps)

### Deleting Apps

!!! info ""
  You are only able to delete Apps from your Parse.com dashboard.
