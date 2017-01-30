## Health Check Kazoo Applications



Connect to the Erlang `kazoo_apps` shell:
 
`kazoo_apps/conn-to-apps.sh`
 
Flushing the cache (callflows, CID, ect):
 
`wh_cache:flush().`
 
Flushing the `config` (db cached system config) requires restart of `sysconf whapp`:
``` 
kzapps_config:flush().
kzapps_controller:restart_app(sysconf).
``` 

**Erlang**-based Application list (full):
 
`application:which_applications().`
 
Start, stop **WhApps** and verify running **WhApps**:
``` 
kzapps_controller:start_app(crossbar).
kzapps_controller:stop_app(crossbar).
kzapps_controller:running_apps().
``` 

Determine which **CouchDB/BIGCouch** server it is connected to
``` 
couch_mgr:get_host().
couch_mgr:get_creds().
```

Forcing Compaction
``` 
couch_compactor:start_link().
couch_compactor:force_compaction().
``` 

Determine which **RabbiMQ** you are connecting to:
``` 
amqp_mgr:get_host().
amqp_mgr:is_available().
 ```

**Stepswitch** Commands
 ```
stepswitch_maintenance:reconcile().
stepswitch_maintenance:reconcile(ACCOUNT_ID).
stepswitch_maintenance:reload_resources().
stepswitch_maintenance:lookup_number(5552223333).
stepswitch_maintenance:process_number(5552223333).
 ```

**Whapps** Maintenance (useful for updating the global views in **BigCouch** on an install)
```
kzapps_maintenance:refresh().
kzapps_maintenance:refresh(Account ID).
```

NOTE - THIS REPLACED:

`crossbar:refresh().`

Callflow Refresh Command (useful for after upgrade)
 
`callflow_maintenance:refresh().`
 
Whistle Number Manager (iterates thru each account checking all DID's exist in the numbers db)
 
`kazoo_number_manager_maintenance:reconcile().`
