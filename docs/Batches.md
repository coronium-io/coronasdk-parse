<style>.codehilite{padding-bottom:6px;}</style>

# Object Batching

Parse allows batching of certain operations on Objects. You can send up to 50 __create__, __update__, or __delete__ calls using the batch method.

## .new

Create a new batch instance to populate with actions.

```lua
  local b = parse.batch.new()
```

## .create

Add a `create` action to the batch instance.

*Parameters:*

* __className__
* __dataTable__

```lua
  b.create( "Toys", { kind = car, color = red, stock = 23 } )
```

## .update

Add an `update` action to the batch instance.

*Parameters:*

* __className__
* __objectId__
* __dataTable__

```lua
  b.update( "Toys", "123abc", { stock = 20 } )
```

## .delete

Add a `delete` action to the batch instance.

*Parameters:*

* __className__
* __objectId__

```lua
  b.delete( "Toys", "123abc" )
```

## .getCount

Get the current action count in the batch instance. Parse imposes a 50 action limit per batch transaction.

```lua
  local action_count = b.getCount()
```

## .getBatch

Returns the current batch instance data table for sending to Parse.

```lua
  local batch_data = b.getBatch()
```

# Example

You can mix up to 50 create, update, and delete actions per batch. Batching is limited to __Objects__ only as per the Parse specification.

```lua
  -- Build the batch
  local b = parse.batch.new()
  b.create( "Toys", { kind = car, color = red } )
  b.create( "Parts", { wheels = 4 } )
  b.update( "Toys", "123abc", { color = blue } )
  b.delete( "Parts", "abc123" )
  -- Send off the batch
  parse.request( parse.Object.batch )
  :data( b.getBatch() )
  :response(function( ok, res )
    if not ok then
      print( 'err', res )
    else
      for _, result in ipairs( res ) do
        if result.success then
          print( result.success.createdAt )
        else
          print( result.error.error, result.error.code )
        end
      end
    end
  end)
```

The response is returned in a table array, with the same amount of entry results as sent. Read more about the returns that come back from batch calls by following the link below.

[guide#objects-batch-operations](https://parse.com/docs/rest/guide#objects-batch-operations)
