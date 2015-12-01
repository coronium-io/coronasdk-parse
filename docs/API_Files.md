# Files [parse.File]

!!! warning "File URIs"
    When you upload a file, Parse will return a special url pointing to your resource. Make sure you store or link it to an Object.

## parse.upload()

Upload a file.

!!! info "Important"
  This is a special method, it is accessed directly from the __parse__ namespace, `parse.upload( args )`. It is not a standard `parse.request`.

*Parameters*

* __filename.ext__
* __baseDirectory__ (optional, default: `system.DocumentsDirectory`)


___The baseDirectory is the source directory where your file resides.___

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
  :response(function( ok, res, info )
    print('all done')
    parse.trace( res )
  end)
```

---

## parse.download()

Download a file.

!!! info "Important"
  This is a special method, it is accessed directly from the __parse__ namespace, `parse.download( args )`. It is not a standard `parse.request`.

*Parameters*

* __parse_file_uri__
* __save_as_filename.ext__
* __baseDirectory__ (optional, default: `system.DocumentsDirectory`)

___The baseDirectory is the destination directory of the download.___

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
  :response(function( ok, res, info )
    print('all done')
    parse.trace( res )
  end)
```

---

!!! info ""
  *The following methods __do__ use the common `parse.request` access.*

## Linking files

See [.linkFileToUser](Macros/#linkfiletouser)

---

## .delete

Delete a File.

* Parse provided file uri.

```lua
  parse.request( parse.File.delete, "http://path-to-file" )
  :response(cb)
```
