<style>.codehilite{padding-bottom:6px;}</style>

# Config [parse.config]

Configuration methods are both "getters" and "setters":

```lua
  -- getter
  local appId = parse.config:applicationId()
  -- setter
  parse.config:applicationId("fbf3960f-9bc1-4d10-ab0f-a3eb76e19553")
```

# Application Keys

## :cloudAddress

Set the external Parse-Server address. Default is Parse.com API.

*Parameters:*

* __url_or_ip__ (String)

```lua
  parse.config:cloudAddress( "https://my.parse.server:1234/v1" )
```

## :applicationId

The Parse application identifier to access.

*Parameters:*

* __app_id__ (String, Required)

```lua
  parse.config:applicationId( "fbf3960f-9bc1-4d10-ab0f-a3eb76e19553" )
```

## :restApiKey

The Parse application REST API identifier.

*Parameters:*

* __rest_api_key__ (String, Required)

```lua
  parse.config:restApiKey( "fbf3960f-9bc1-4d10-ab0f-a3eb76e19553" )
```

## :installationId

An installation id to pair with user sessions.

*Parameters:*

* __installation_id__ (String)

```lua
  parse.config:installationId( "fbf3960f-9bc1-4d10-ab0f-a3eb76e19553" )
```

# Debugging

## :debugEnable

Print incoming request data to the terminal.

*Parameters:*

* __is_enabled__ (Boolean) default: FALSE

```lua
  parse.config:debugEnable( true )
```

## :debugVerbose

Print all incoming data to the terminal.

*Parameters:*

* __is_enabled__ (Boolean) default: FALSE

```lua
  parse.config:debugVerbose( true )
```

# Other

## :timeout

Maximum time to wait for a response in seconds.

*Parameters:*

* __seconds__ (Number) default: 30

```lua
  parse.config:timeout( 60 )
```
