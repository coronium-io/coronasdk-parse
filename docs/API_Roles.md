# Roles [parse.Role]

!!! warning "Using Parse-Server?"
    __The self-hosted Parse-Server does not support the Roles module.__

## .get

Get a Role.

*Parameters:*

* __objectId__

```lua
  parse.request( parse.Role.get, "1234abcd" )
  :response(cb)
```

[rest/guide#roles-retrieving-roles](https://www.parse.com/docs/rest/guide#roles-retrieving-roles)

## .create

Create a new Role.

```lua
  parse.request( parse.Role.create )
  :data( { color = "Red", name = "Jingles" } )
  :response(cb)
```

[rest/guide#roles-creating-roles](https://www.parse.com/docs/rest/guide#roles-creating-roles)

## .update

Update a Role.

*Parameters:*

* __objectId__

```lua
  parse.request( parse.Role.update, "Ex4UOSca" )
  :response(cb)
```

[rest/guide#roles-updating-roles](https://www.parse.com/docs/rest/guide#roles-updating-roles)

## .delete

Deletes an Object.

*Parameters:*

* __objectId__

```lua
  parse.request( parse.Role.delete, "Ex4UOSca" )
  :response(cb)
```

[rest/guide#roles-deleting-roles](https://www.parse.com/docs/rest/guide#roles-deleting-roles)
