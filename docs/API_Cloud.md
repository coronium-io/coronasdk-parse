# Cloud [parse.Cloud]

## .call

Call a Cloud function.

*parameters:*

* __functionName__

```lua
  parse.request( parse.Cloud.call, "functionName" )
  :response(cb)
```

## .job

Start up a Cloud Job.

*parameters:*

* __jobName__

```lua
  parse.request( parse.Cloud.job, "jobName" )
  :response(cb)
```
