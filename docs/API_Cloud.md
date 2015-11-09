# Cloud [parse.Cloud]

## .call

Call a Cloud function.

*parameters:*

* __functionName__

```lua
  parse.request( parse.Cloud.call, "follow" )
  :data({username="Charles"})
  :response(cb)
```

[rest/guide#cloud-code-cloud-functions](https://www.parse.com/docs/rest/guide#cloud-code-cloud-functions)

## .job

Start up a Cloud Job.

*parameters:*

* __jobName__

```lua
  parse.request( parse.Cloud.job, "userMigration" )
  :data({plan="paid"})
  :response(cb)
```

[rest/guide#cloud-code-background-jobs](https://www.parse.com/docs/rest/guide#cloud-code-background-jobs)
