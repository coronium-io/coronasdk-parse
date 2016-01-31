<style>.codehilite{padding-bottom:6px;}</style>

# Tools [parse.tools]

## .generateInstallationId

Generate an installation identifier from string key that is Parse compatible.

*Parameters:*

* __input__

```lua
  local id = parse.tools.generateInstallationId( "a_string_input" )
```

## More Tools

`.b64( string )`

Base encode a string.

`.trace( string )`

Print a value to the terminal

`.escape( uri_string )`

Escape a URI string.

`.unescape( escaped_str )`

Unescape a string.

`.json2table( json_str )`

Convert JSON to Lua Table.

`.table2json( lua_table )`

Convert Lua Table to JSON.

`.timestampToISODate( ts )`

Convert a timestamp to ISO date. Leave parameter empty to use the current time.
