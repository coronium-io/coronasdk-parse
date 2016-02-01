<style>.codehilite{padding-top:2px;padding-bottom:6px;}</style>

__A Parse.com and Parse-Server plugin for Corona SDK development.__

*Release 0.2.7*

<a href="https://twitter.com/share" class="twitter-share-button" data-url="http://parse.develephant.com" data-text="Parse plugin for Corona SDK" data-via="develephant" data-size="large" data-related="coronalabs" data-hashtags="parseit">Tweet</a>
<script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+'://platform.twitter.com/widgets.js';fjs.parentNode.insertBefore(js,fjs);}}(document, 'script', 'twitter-wjs');</script>

# Welcome

!!! important
    Read through the [__Parse REST API guide__](https://www.parse.com/docs/rest/guide) at Parse.com to understand how the Parse REST API works.

## Quick Start

When you build using the Corona Simulator, the server automatically takes care of integrating the plugin into your project.

All you need to do is add an entry into a plugins table of your __build.settings__. The following is an example of a minimal build.settings file:

```lua
settings =
{
    plugins =
    {
        -- key is the name passed to Lua's 'require()'
        ["plugin.parse"] =
        {
            -- required
            publisherId = "com.develephant",
        },
    },      
}
```

Create a __main.lua__ and fill it like so:

```lua
local parse = require('plugin.parse')
--== Using self-hosted Parse-Server (optional)
parse.config:cloudAddress("https://your.parse.server:PORT/API_PREFIX")
--== Application Keys
parse.config:applicationId("PARSE_APP_ID")
parse.config:restApiKey("PARSE_REST_KEY")

--create an Object
parse.request( parse.Object.create, "Blocks" )
:data( { color = "Red", round = false } )
:response(function(ok, res)
  if ok then
    parse.trace( res ) --prints pretty table
  end
end)
```

__If you have :debugEnabled, you can leave out the callback while your testing.__

```lua
...
parse.config:debugEnabled( true )
...
parse.request( parse.Object.query, "Blocks" )
:where({ color = "red" })
:response()
```

The response data will print out into the terminal.

## Using the Plugin

__[Click Here to Read the Developer Guide](CH1_Usage.md)__

---

## API Directory

### Parse API

#### [Objects](API_Objects.md)
#### [Users](API_Users.md)
#### [Sessions](API_Sessions.md)
#### [Roles](API_Roles.md)
#### [Files](API_Files.md)
#### [Analytics](API_Analytics.md)
#### [Push](API_Push.md)
#### [Installations](API_Installations.md)
#### [Config](API_Config.md)
#### [Cloud](API_Cloud.md)
#### [Schemas](API_Schemas.md)
#### [Apps](API_Apps.md)
#### [Hooks](API_Hooks.md)
#### [Triggers](API_Triggers.md)

### Extended API

#### [Batches](Batches.md)
#### [Config/Debug](Config.md)
#### [Macros](Macros.md)
#### [Tools](Tools.md)
