# Schemas [parse.Schema]

## .get

Get a Schema from Parse.

*Parameters:*

* __schemaName__

```lua
  parse.request( parse.Schema.get, "schemaName" )
  :response(cb)
```

[rest/guide#schemas-fetch-the-schema](https://www.parse.com/docs/rest/guide#schemas-fetch-the-schema)

## .getAll

Get all Schemas.

```lua
  parse.request( parse.Schema.getAll )
  :response(cb)
```

[rest/guide#schemas-fetch-the-schema](https://www.parse.com/docs/rest/guide#schemas-fetch-the-schema)

## .create

Create a new Schema.

*Parameters:*

* __schemaName__

```lua
  parse.request( parse.Schema.create, "schemaName" )
  :response(cb)
```

[rest/guide#schemas-adding-a-schema](https://www.parse.com/docs/rest/guide#schemas-adding-a-schema)

## .update

Update a Schema.

*Parameters:*

* __schemaName__

```lua
  parse.request( parse.Schema.update, "schemaName" )
  :response(cb)
```

[rest/guide#schemas-modifying-the-schema](https://www.parse.com/docs/rest/guide#schemas-modifying-the-schema)

## .delete

Deletes a Schema.

*Parameters:*

* __schemaName__

```lua
  parse.request( parse.Object.delete, "schemaName" )
  :response(cb)
```

[rest/guide#schemas-removing-a-schema](https://www.parse.com/docs/rest/guide#schemas-removing-a-schema)
