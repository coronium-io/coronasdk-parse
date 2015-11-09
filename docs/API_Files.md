# Files [parse.File]

!!! warning "File URIs"
    When you upload a file, Parse will return a special url pointing to your resource. Make sure you store or link it to an Object.

## .upload

Upload a file.

!!! info "Important"
  This is a special method, it is accessed directly from then parse namespace, __parse.upload( args )__. It is not a standard `parse.request`.

*Parameters*

* __filename.ext__
* __baseDirectory__ (optional, default: system.DocumentsDirectory)

!!! note
  The baseDirectory is the source directory where your file resides.

```lua
  parse.upload( "filename.ext" )
  :response()
```

You can also follow the progress of the upload:

```lua
  parse.upload( "filename.ext", system.DocumentsDirectory )
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

---

## .download

Download a file.

!!! info "Important"
  This is a special method, it is accessed directly from then parse namespace, __parse.download( args )__. It is not a standard `parse.request`.

*Parameters*

* __parse_file_uri__
* __save_as_filename.ext__
* __baseDirectory__ (optional, default: system.DocumentsDirectory)

!!! note
  The baseDirectory is the destination directory of the download.

```lua
  parse.download( "https://files.parsefss.com/...", "filename.ext" )
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

---

*The following methods __do__ use the common `parse.request` access.*

## .link

Link a file.

*Parameters:*

* __class__

```lua
  parse.request( parse.File.link, "Pets" )
  :response(cb)
```

---

## .delete

Delete a File.

* Parse provided file uri.

```lua
  parse.request( parse.File.delete, "http://path-to-file" )
  :response(cb)
```
