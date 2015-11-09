# Installations [parse.Installation]

## .get

Get an Installation from Parse.

*Parameters:*

* __objectId__

```lua
  parse.request( parse.Installation.get, "1234abcd" )
  :response(cb)
```

[rest/guide#push-notifications-retrieving-installations](https://www.parse.com/docs/rest/guide#push-notifications-retrieving-installations)

## .query

Perform an Installation Query.

```lua
  parse.request( parse.Installation.query )
  :where( { color = "Brown" } )
  :response(cb)
```

[rest/guide#push-notifications-querying-installations](https://www.parse.com/docs/rest/guide#push-notifications-querying-installations)

## .create

Create a new Installation.

```lua
  parse.request( parse.Installation.create )
  :data( { color = "Red", name = "Jingles" } )
  :response(cb)
```

[rest/guide#push-notifications-installations](https://www.parse.com/docs/rest/guide#push-notifications-installations)

## .update

Update an Installation by `objectId`.

*Parameters:*

* __objectId__

```lua
  parse.request( parse.Installation.update, "Ex4UOSca" )
  :set("color", "Blue")
  :response(cb)
```

[rest/guide#push-notifications-updating-installations](https://www.parse.com/docs/rest/guide#push-notifications-updating-installations)

## .delete

Deletes an Installation by `objectId`.

*Parameters:*

* __objectId__

```lua
  parse.request( parse.Installation.delete, "Ex4UOSca" )
  :response(cb)
```

[rest/guide#push-notifications-deleting-installations](https://www.parse.com/docs/rest/guide#push-notifications-deleting-installations)
