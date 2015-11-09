# Sessions [parse.Session]

## .me

Get the logged in Session.

> The User must be logged in.

```lua
  parse.request( parse.Session.me )
  :response(cb)
```

[rest/guide#sessions-retrieving-sessions](https://www.parse.com/docs/rest/guide#sessions-retrieving-sessions)

## .get

Get an Session by `objectId`.

*Parameters:*

* __objectId__

```lua
  parse.request( parse.Session.get, "1234abcd" )
  :response(cb)
```

[rest/guide#sessions-retrieving-sessions](https://www.parse.com/docs/rest/guide#sessions-retrieving-sessions)

## .query

Get Session(s) by Query. To fetch all, pass empty table to the `:where` method.

```lua
  parse.request( parse.Session.query )
  :where( { color = "Red" } )
  :response(cb)
```

[rest/guide#sessions-querying-sessions](https://www.parse.com/docs/rest/guide#sessions-querying-sessions)

## .update

Update a Session by `objectId`.

```lua
  parse.request( parse.Session.update, "1234abcd" )
  :data( { color = "Yellow" } )
  :response(cb)
```

[rest/guide#sessions-updating-sessions](https://www.parse.com/docs/rest/guide#sessions-updating-sessions)

## .delete

Delete a Session by `objectId`.

```lua
  parse.request( parse.Session.delete, "1234abcd" )
  :response(cb)
```

[rest/guide#sessions-deleting-sessions](https://www.parse.com/docs/rest/guide#sessions-deleting-sessions)

## .logout

Alias to `User` logout.

```lua
  parse.request( parse.Session.logout )
  :response(cb)
```

[rest/guide#sessions-deleting-sessions](https://www.parse.com/docs/rest/guide#sessions-deleting-sessions)
