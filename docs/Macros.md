<style>.codehilite{padding-bottom:6px;}</style>

# Macros [parse.macro]

While the Parse plugin allows you to go deep into the REST API, there is always room for shortcuts. Macros allow you to perform pre-built functionality that extends the Parse REST API specification.

You can also add your own Macros that can be used globally wherever you can access the parse object. There are a number of common Macros that come by default.

### Users

## .findUserById

Finds a User by supplied id.

*Parameters:*

* __userId__ (objectId)

```lua
  parse.macro.findUserById( 'user_id' )
  :response(cb)
```

## .findUserByEmail

Finds a User by supplied email.

*Parameters:*

* __email__

```lua
  parse.macro.findUserByEmail( 'user@email.com' )
  :response(cb)
```

## .findUserByUsername

Finds a User by supplied username.

*Parameters:*

* __username__

```lua
  parse.macro.findUserByUsername( 'user_name' )
  :response(cb)
```

### Linking

## .linkObjectToUser

Link an arbitrary Object to a User.

*Parameters:*

* __linkColLabel__
* __className__
* __objectId__
* __userId__ (objectId)

```lua
  parse.macro.linkObjectToUser('toy', 'Toys', 'toy_id', 'user_id')
  :response(cb)
```

## .linkFileToUser

Link an uploaded File object to a User.

*Parameters:*

* __fileColLabel__
* __fileUri__
* __userId__ (objectId)

```lua
  parse.macro.linkFileToUser('avatar', 'file_uri', 'user_id')
  :response(cb)
```

!!! note
  The __fileUri__ is returned when a file is uploaded. You can find it in the `name` key in the response.

## .linkInstallationToUser

Link an Installation to a User.

*Parameters:*

* __installColLabel__
* __installId__ (objectId)
* __userId__ (objectId)

```lua
  parse.macro.linkInstallationToUser('user', 'installation_id', 'user_id')
  :response(cb)
```

## .linkFileToObject

Link a File to an arbitrary Object.

*Parameters:*

* __fileColLabel__
* __fileUri__
* __className__
* __objectId__

```lua
  parse.macro.linkFileToObject('snapshot', 'file_uri', 'Pics', 'pic_id')
  :response(cb)
```

## .linkUserToObject

Link a User to an arbitrary Object.

*Parameters:*

* __userColLabel__
* __className__
* __objectId__
* __userId__ (objectId)

```lua
  parse.macro.linkUserToObject('user', 'Runners', 'runner_id', 'user_id')
  :response(cb)
```

## .linkObjectToUser

Link an arbitrary Object to a User.

*Parameters:*

* __objectColLabel__
* __className__
* __objectId__
* __userId__ (objectId)

```lua
  parse.macro.linkObjectToUser('food', 'Food', 'food_id', 'user_id')
  :response(cb)
```

## .linkObjects

Links one Object to another.

*Parameters:*

* __objectColLabel__
* __className__
* __objectId__
* __toClassName__
* __toObjectId__

```lua
  parse.macro.linkObjects('ageGroup', 'Toy', 'toy_id', 'Group', 'group_id')
  :response(cb)
```

---

### Counters

Counters allow in place number increment and decrement. To add to the column property supply a positive number. To decrease the value, use a negative number. This will only function properly on number based columns.

## .updateCounter

*Parameters:*

* __counterColLabel__
* __amount__ (can be negative)
* __className__
* __objectId__

___Adding 1 to the score column___
___Adding 1 to the score column___

```lua
  parse.macro.updateCounter('score', 1, 'Scores', 'score_id')
  :response(cb)
  -- score is now 1
```

___Adding 10 to the score column___
___Adding 10 to the score column___

```lua
  parse.macro.updateCounter('score', 10, 'Scores', 'score_id')
  :response(cb)
  -- score is now 11
```

___Removing 5 from the score column___
___Removing 5 from the score column___

```lua
  parse.macro.updateCounter('score', -5, 'Scores', 'score_id')
  :response(cb)
  -- score is now 6
```

---

### Columns

Parse supports a number of special columns that you can run unique queries on. These Macros help in the creation of these columns.

## .addPointerCol

Add a Pointer column. This column is used to link objects.

*Parameters:*

* __pointerColLabel__
* __pointerClass__ (className)
* __pointerId__ (objectId)
* __className__
* __objectId__

```lua
  parse.macro.addPointerCol('car', 'Garage', 'garage_id', 'Car', 'car_id')
  :response(cb)
```

## .addRelationCol

Add a Relation Column. Creates relations between Class types.

*Parameters:*

* __relationColLabel__
* __relatedClassName__
* __className__
* __objectId__

```lua
  parse.macro.addRelationCol('related', 'Vintage', 'Toys', 'toy_id')
  :response(cb)
```

## .addGeoPointCol

Add a GeoPoint column allowing for specialized location queries.

*Parameter:*

* __geoPointColLabel__
* __latitude__ (Number)
* __longitude__ (Number)
* __className__
* __objectId__

```lua
  parse.macro.addGeoPointCol('location', 30.0, -40.0, 'Sales', 'sales_id')
  :response(cb)
```

## .addBinaryCol

Add a Binary column for storing Base64 encoded data.

*Parameters:*

* __binaryColLabel__
* __base64Data__

```lua
  parse.macro.addBinaryCol( 'db_data', db_backup_b64_str )
  :response(cb)
```

## .addDateCol

Adds an ISO compliant Date column.

*Parameters:*

* __dateColLabel__
* __isoDate__
* __className__
* __objectId__

```lua
  parse.macro.addDateCol('birthday', iso_date, parse.Type.User, 'user_id')
  :response(cb)
```

!!! note "ISO Dates"
  Parse is very specific about its Date format. You can generate a valid date using `parse.tools.timestampToISODate()`. See [.timestampToISODate](#)

---

### Auth Data

## .addTwitterAuth

Add Twitter Authentication data to a User.

*Parameters:*
* __authDataTable__
* __userId__ (objectId)

```lua
  local auth_data =
  {
    id = "12345678",
    screen_name = "ParseIt",
    consumer_key = "SaMpLeId3X7eLjjLgWEw",
    consumer_secret = "SaMpLew55QbMR0vTdtOACfPXa5UdO2THX1JrxZ9s3c",
    auth_token = "12345678-SaMpLeTuo3m2avZxh5cjJmIrAfx4ZYyamdofM7IjU",
    auth_token_secret = "SaMpLeEb13SpRzQ4DAIzutEkCE2LBIm2ZQDsP3WUU"
  }

  parse.macro.addTwitterAuth( auth_data, 'user_id' )
  :response(cb)
```

## .addFacebookAuth

Add Facebook Authentication data to a User.

*Parameters:*

* __authDataTable__
* __userId__ (objectId)

```lua
  local auth_data =
  {
    id = "123456789",
    access_token = "SaMpLeAAibS7Q55...",
    expiration_date = "2012-02-28T23:49:36.353Z"
  }
  
  parse.macro.addFacebookAuth( auth_data, 'user_id' )
  :response(cb)
```

## .addAnonAuth

Add a UUID as a custom authentication method.

*Parameters:*

* __uuid__ (lowercase-alpha-numeric)
* __userId__ (objectId)

```lua
  parse.macro.addAnonAuth('uo3m2avzxh5cj...', 'user_id')
  :response(cb)
```

### Searches

## .findWhereGreater

Find a Class key greater than the supplied value.

*Parameters:*

* __className__
* __key__
* __value__

```lua
  parse.macro.findWhereGreater( 'Toys', 'stock', 12 )
  :response(cb)
```

## .findWhereLess

Find a Class key less than the supplied value.

*Parameters:*

* __className__
* __key__
* __value__

```lua
  parse.macro.findWhereLess( 'Toys', 'stock', 3 )
  :response(cb)
```

## .findWhereEqual

Find a Class key equal to the supplied value.

*Parameters:*

* __className__
* __key__
* __value__

```lua
  parse.macro.findWhereEqual( 'Toys', 'kind', 'car' )
  :response(cb)
```

## .findWhereEqualOrGreater

Find a Class key equal to or greater than the supplied value.

*Parameters:*

* __className__
* __key__
* __value__

```lua
  parse.macro.findWhereEqualOrGreater( 'Toys', 'stock', 5 )
  :response(cb)
```

## .findWhereEqualOrLess

Find a Class key equal to or less than the supplied value.

*Parameters:*

* __className__
* __key__
* __value__

```lua
  parse.macro.findWhereEqualOrLess( 'Toys', 'stock', 5 )
  :response(cb)
```

## .findWhereNotEqual

Find a Class key __not__ equal to the supplied value.

*Parameters:*

* __className__
* __key__
* __value__

```lua
  parse.macro.findWhereNotEqual( 'Toys', 'color', 'red' )
  :response(cb)
```

## .findWhereTrue

Find a Class key equal to __true__.

*Parameters:*

* __className__
* __key__

```lua
  parse.macro.findWhereTrue( 'Toys', 'new' )
  :response(cb)
```

## .findWhereFalse

Find a Class key equal to __false__.

*Parameters:*

* __className__
* __key__

```lua
  parse.macro.findWhereFalse( 'Toys', 'inStock' )
  :response(cb)
```

### Geo Searches

___Geo Searches require a [GeoPoint](API_GeoPoint) column on the class.___

## .geoSearchWithinBoundary

Find Objects within the given coordinates. You must provide two GeoPoints; one for the southwest corner, and one for the northwest corner. This creates your boundary.

*Parameters:*

* __className__
* __southwestLatitude__
* __southwestLongitude__
* __northeastLatitude__
* __northeastLongitude__

```lua
  parse.macro.geoSearchWithinBoundary( 'Sales', 10.0, -23.0, 22.0, -11.0 )
  :response(cb)
```

## .geoSearchWithinRadius

Find Objects within given radius. Max distance is 100 miles.

*Parameters:*

* __className__
* __latitude__
* __longitude__

```lua
  parse.macro.geoSearchWithinRadius( 'Sales', 10.0, -23.0 )
  :response(cb)
```

## .geoSearchWithinMiles

Find Objects in a radius, within the specified miles.

*Parameters:*

* __className__
* __latitude__
* __longitude__
* __withinMiles__ (100 max)

```lua
  parse.macro.geoSearchWithinMiles( 'Sales', 10.0, -20.0, 5 )
  :response(cb)
```

## .geoSearchWithinKms

Find Objects in a radius, within the specified kilometers.

*Parameters:*

* __className__
* __latitude__
* __longitude__
* __withinKms__

```lua
  parse.macro.geoSearchWithinKms( 'Sales', 10.0, -20.0, 15 )
  :response(cb)
```

## .geoSearchWithinRadians

Find Objects in a radius, within the specified radians.

*Parameters:*

* __className__
* __latitude__
* __longitude__
* __withinRadians__

```lua
  parse.macro.geoSearchWithinRadians( 'Sales', 10.0, -20.0, 123 )
  :response(cb)
```

# Custom Macros

Creating your own Macros is very simple and allows you to reuse calls throughout your application.

A Macro is basically just a returned `parse.request` without the `:response` method attached to it. The response is added when you actually use the Macro.

___Adding a Macro___

## .add

Adds a new request Macro to the system.

*Parameters:*

* __macroName__ (no spaces)
* __macroRequest__

```lua
  parse.macro.add( "getUsersOlderThan", function( age )
    return parse.request( parse.User.query )
    :where( { age = ["$gt"] = age } )
  end)
```

___Using a Macro___

Once you've added your Macro, you can call it anywhere you can access the parse object. Here is where the `:response` gets added as well.

```lua
  parse.macro.getUsersOlderThan( 30 )
  :response(cb)
```

___Removing a Macro___

## .remove

*Parameters:*

* __macroName__

In the rare case you need to remove a Macro:

```lua
  parse.macro.remove( "getUsersOlderThan" )
  -- If you try to call this Macro now, you
  -- will get a runtime error. So beware.
```
