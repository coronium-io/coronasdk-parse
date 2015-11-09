# Files [parse.File]

!!! warning "File URIs"
    When you upload a file, Parse will return a special url pointing to your resource. Make sure you store or link it to an Object.

## .upload

Upload a file.

*Parameters*

* __filename.ext__
* __baseDirectory__

```lua
  parse.upload( "filename.ext", system.DocumentsDirectory )
  :response()
```

You can also follow the progress of the upload:

```lua
  parse.updload( "filename.ext", system.DocumentsDirectory )
  :progress(function(ok, bytesTrans, bytesEst)
    if ok then
      print( bytesTrans, bytesEst)
    end
  end)
  :response(function( res )
    print('all done')
    parse.trace( res )
  end)
```

## .download

Upload a file.

*Parameters*

* __parse_file_uri__
* __save_as_filename.ext__
* __baseDirectory__ (optional, default: system.DocumentsDirectory)

```lua
  parse.download( "https://files.parsefss.com/...", "filename.ext", system.DocumentsDirectory )
  :response()
```

You can also follow the progress of the download:

```lua
  parse.download( "https://files.parsefss.com/...", "filename.ext", system.DocumentsDirectory )
  :progress(function(ok, bytesTrans, bytesEst)
    if ok then
      print( bytesTrans, bytesEst)
    end
  end)
  :response(function( res )
    print('all done')
    parse.trace( res )
  end)
```

## .link

Link a file.

*Parameters:*

* __class__

```lua
  parse.request( parse.File.link, "Pets" )
  :response(cb)
```

## .delete

Delete a File.

* Parse provided file uri.

```lua
  parse.request( parse.File.delete, "http://path-to-file" )
  :response(cb)
```
