# Objects [parse.Object]

## .get

Get an Object from Parse.

*Parameters:*

* __class__
* __objectId__

```lua
  parse.request( parse.Object.get, "Pets", "1234abcd" )
  :response(cb)
```

[rest/guide#objects-retrieving-objects](https://www.parse.com/docs/rest/guide#objects-retrieving-objects)

## .query

Perform an Object Query.

*Parameters:*

* __class__

```lua
  parse.request( parse.Object.query, "Pets" )
  :where( { color = "Brown" } )
  :response(cb)
```

https://www.parse.com/docs/rest/guide#queries

## .create

Create a new Object.

*Parameters:*

* __class__

```lua
  --== Creating an Object
  --== Using `:set`
  parse.request( parse.Object.create, "Pets" )
  :set("color", "Red")
  :set("name", "Jingles")
  :response(cb)

  --== OR
  --== Using `:data`
  parse.request( parse.Object.create, "Pets" )
  :data( { color = "Red", name = "Jingles" } )
  :response(cb)

  --== OR
  --== Using `:data` with JSON string
  parse.request( parse.Object.create, "Pets" )
  :data( [[{"color":"Red","name":"Jingles"}]] )
  :response(cb)
```

[rest/guide#objects-creating-objects](https://www.parse.com/docs/rest/guide#objects-creating-objects)

## .update

Update an Object.

*Parameters:*

* __class__
* __objectId__

```lua
  parse.request( parse.Object.update, "Pets", "Ex4UOSca" )
  :set("color", "Blue")
  :response(cb)
```
See `.create` above for other usages with Lua tables, and JSON strings.

[rest/guide#objects-updating-objects](https://www.parse.com/docs/rest/guide#objects-updating-objects)

## .delete

Deletes an Object.

*Parameters:*

* __class__
* __objectId__

```lua
  parse.request( parse.Object.delete, "Pets", "Ex4UOSca" )
  :response(cb)
```

[rest/guide#objects-deleting-objects](https://www.parse.com/docs/rest/guide#objects-deleting-objects)
