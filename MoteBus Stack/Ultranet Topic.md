# Ultranet Topic 

## Mote
| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:------------ |:-----------|:-------|
| mote://bash            |            |        |
| mote://xstorage        |            |        |
| mote://nearby          |            |        |
| mote://drop            |            |        | 
| mote://shot            |            |        |
| mote://measure         |            |        |
| mote://qsnap           |            |        |
| mote://apt             |            |        |
| mote://time            |            |        |
| mote://setUser         |            |        |
| mote://getUser         |            |        |
| mote://listPeripherals |            |        |
| mote://env             |            |        |
| mote://schedule        |            |        |
| mote://window          |            |        |
| mote://keybot          |            |        |
| mote://audio           |            |        |
| mote://shortcut        |            |        |
   

## Qbix
**mpodman**
   
 | <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
   |:---------------- |:----------- |:------- |
   | helm://list      | list releases (= mpod_name)| {"namespace":"default"} |
   | helm://create    | create a new chart_name with the given mpod_name. There are **5** kinds of chart_name  written in "mpodman/xxxx". (xxxx can be **fbuilder, sscreen, ioc, fbots** or **webmms-srv**) | { "releaseName": "fbots", "chartName": "mpodman/fbots", "namespace": "default", "values": { "MCHAT_EINAME": "fbots-example", "MCHAT_APPNAME": "fbots-example-app", "FBOT_QNAME": "comm", "fbots.ingress.enabled": "true", "fbots.ingress.hosts[0]": "yh.ypcloud.com", "fbots.ingress.path": "/fbots/(.*)" } } |
   | helm://delete    |  uninstall a release | { "releaseName": "fbots", "namespace": "default" } |
   | helm://update    | update a new chart_name with the given mpod_name. There are **5** kinds of chart_name  written in "mpodman/xxxx". (xxxx can be **fbuilder, sscreen, ioc, fbots** or **webmms-srv**) | { "releaseName": "fbots", "chartName": "mpodman/fbots", "namespace": "default", "values": { "MCHAT_EINAME": "fbots-example", "MCHAT_APPNAME": "fbots-example-app", "FBOT_QNAME": "comm", "fbots.ingress.enabled": "true", "fbots.ingress.hosts[0]": "yh.ypcloud.com", "fbots.ingress.path": "/fbots/(.*)" } } |
   | helm://get       | download extended information of a named release  | { "releaseName": "fbuilder", "namespace": "default", "subCommand": "all" } |
   | helm://history   | fetch release history | { "releaseName": "fbuilder", "namespace": "default" } |
   | helm://rollback  | roll back a release to a previous revision | { "releaseName": "fbuilder", "namespace": "default" } |
   | helm://status    | display the status of the named release  | { "releaseName": "fbuilder", "namespace": "default" } |
   | kubectl://deletePod | delete resources by filenames, stdin, resources and names, or by resources and label selector | { "pod_name": "mpod-810moj7dp6e-0", "namespace": "default" } |
   | kubectl://getPod | read the specified Pod | { "pod_name": "mpod-810moj7dp6e-0", "namespace": "default" } |
   | kubectl://getPodLog | read log of the specified Pod | {"pod_name":"mpod-810moj7dp6e-0","namespace":"default","container":""} |
   | kubectl://listPod | list or watch objects of kind Pod | {"namespace":"default"} |
   | kubectl://createNamespace | create a Namespace | {"namespace":"system"} |
   | kubectl://deleteNamespace | Delete a Namespace | {"namespace":"system"} |
   | kubectl://getNamespace | read the specified Namespace | {"namespace":"system"} |
   | kubectl://listNamespace | list or watch objects of kind Namespace | {} |   
  
**qman**
1. qbix

| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:------------------ | ----------- | ------- |
| qbix://list   | list objects kind of qbix | { "site_name": "h1-qbix", "qbix_type": "qoci", "payload": {} } |
| qbix://run    | run a qbix | { "site_name": "h2-qbix", "qbix_type": "qoci", "payload": {  } } |
| qbix://add    | add a qbix | { "site_name": "h2-qbix", "qbix_type": "qoci", "payload": {  } } |
| qbix://delete | delete specified qbix | { "site_name": "h2-qbix", "qbix_type": "qoci", "payload": {  } } |
| qbix://get    | read the specified qbix | { "site_name": "twcc-qbix", "qbix_type": "twcc", "payload": { } } |
| qbix://pod    | read the pod info of specified qbix | { "site_name": "twcc-qbix", "qbix_type": "twcc", "payload": { } } |
| qbix://image  | list objects kind of image | { "site_name": "twcc-qbix", "qbix_type": "twcc", "payload": { } } |
| qbix://size   | list object kind of size | { "site_name": "twcc-qbix", "qbix_type": "twcc", "payload": { } } |
| qbix://notify | notify qbix | {"container":"","status":""} |

2. qman

| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:------------------ | ----------- | ------- |
| qman://list   | list objects kind of qsite | {} |
| qman://run    | run a qbix | { "site_name": "any-qbix", "qbix_type": "any", "payload": { } } |
| qman://delete | delete specified qbix | { "site_name": "any-qbix", "qbix_type": "any", "payload": { } } |

3. qociman

| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:------------------ | ----------- | ------- |
| qociman://run | run a new container | {"image":"motebus/fbots:latest","container_name":"test","network_mode":"host","restart":"always","env":{"MCHAT_WATCHLEVEL":1,"MCHAT_APPNAME":"test-app","MCHAT_EINAME":"test","FBOT_QNAME":"test_flows","FBOT_QDATA":null,"FBOT_QTYPE":"projectflows","FBOT_UID":null,"FBOT_MANY":1,"FBOT_CLUSTER":0,"FBOT_MODE":"xstorage","FBOT_UI":"0","TZ":"Asia/Taipei"}} |
| qociman://add | add a new container | {"image":"motebus/fbuilder:1.1.2","network_mode":"host","restart":"always","env":{"TEST":"123"},"ports":{"2020":"2020"}} |
| qociman://delete | remove one container | {"container":"qx-xxx-jujue"} |
| qociman://get | read the specified container | {"container":"qx-xxx-jujue"} |
| qociman://list | list containers | {"filters":{"name":["free"]}} |
| qociman://restart | restart the specified container | {"container":"qx-xxx-jujue"} |   
| qociman://start | start the specified container | {"container":"qx-xxx-jujue"} |   
| qociman://stop | stop the specified container | {"container":"qx-xxx-jujue"} |   
| qociman://status | read status of specified container | {"container":"qx-xxx-jujue"} |      

## Ultra

| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:------------ |:-----------|:-------|   
| portal://log   | create the log record into odoo including 4 fields(name, time, fm, and mesaage) | { "model":"","voucher":"","vid": ,"cmd":"","act":"","data":{"name":"","message":""}}  |
| portal://event | create the event record into odoo |{"model":"","voucher":"","vid": ,"cmd":"","act":"","data":{...}} |
| portal://cost  | create the cost record  | { "model":"","voucher":"","vid": ,"cmd":"","act":"","data":{...}}  |
| portal://form  | create detail data list of device or equipment into odoo | { "model":"","voucher":"","vid": ,"cmd":"","act":"","data":{...}}  |
| query://model  | query data  | { "model":"","voucher":"","vid": ,"cmd":"","act":"","data":{"query_str":[...],"query_rst":[...]}}  |
   
## Jujue

| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:------------ |:-----------|:-------|   
| ss://          |            |        |
| watch://event  |            |        |
| comm://tg      |            |        |
| mod://play     |            |        |
| filter://chart |            |        |

## Others
 
| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:------------ |:-----------|:-------|   
| auto://      |            |        |
| pd://        |            |        |
| play://      |            |        |
   
   
### object store
1. file://topic: function

| <div style="width: 150px">topic | <div style="width: 230px">description | <div style="width: 100px">payload |
|:------------------- |:-----------|:-------:|
| file://addbucket    |             |         |
| file://deletebucket |             |         |
| file://listbucket   |             |         |
| file://set          |             |         |
| file://get          |             |         |
| file://delete       |             |         |
| file://list         |             |         |



2. obj://topic: function

| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:------------ |:-----------|:-------|
| obj://add    | insert object            |{"name": object name,"data": {}}         |
| obj://set    | update object            |{"oid": object oid,"name": object name, "data": {}}         |
| obj://delete | delete object            |{"oid": object oid}         |
| obj://get    | get object               |{"oid": object oid}         |   
| obj://list   | list objects             |{"condition": {"name": object name}  }     |
   


### comm

  | <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
  |:---------------------- |:----------- |:------- |
  | mail:// *address*      |send msg by email             |{"content":mail content,"subject":mail subject}|
  | sms :// *phone number* |send msg by sms             |{"text":sms content}         |
  | tg:// *chat id*        |send msg by tg             |{"content":telegram content,"type":send method, available type :['message','photo','audio','document','video','animation','voice','sticker'], default is 'message',
"from":telegram bot name, available bot:['pinponboybot','jujuebot','lovetubebot','ypcloudbot','ultravisorbot','smartscreenbot'], default is pinponboy,"cc": chat_id of cc (optional),"parse_mode":"MarkdownV2" (optional)}         |
  | ioc:// *chat id*       |send msg by tg with IOC format            |{"content":telegram content,"from":telegram bot name, "to": to_name,"cc": chat_id of cc,options}     |
  | git:// *chat id*       |send msg by tg from git  with IOC format  |:{"content":telegram content,"type":send method,"from":telegram bot name, "cc": chat_id of cc (optional),"parse_mode":"MarkdownV2" (optional)}         |
  | console:// *chat id*   |send object msg  with IOC format          |{"content":telegram content,"from":telegram bot name, "to": to_name,"cc": chat_id of cc,options}     |
  | watch:// *chat id*     |send msg with IOC format from watch       |{"content":telegram content,"from":telegram bot name, "to": to_name,"cc": chat_id of cc,options}     |
  | mpod:// *chat id*      |send msg with IOC format from mpod        |{"content":telegram content,"from":telegram bot name, "to": to_name,"cc": chat_id of cc,options}     |
  | line:// *line id*      | not available            |         |
  | fb:// *fb id*          | not available            |         |
  | sip://                 | not available            |         |
  | mqtt://*mqtt topic*    | not available            |         |
  | echo                   | not available            |         |
  | log://username         |send msg to log           | {"text":log content,"uid": user id(optional)}        |
  | view://username        |send msg to view          | {"text":view content}        |
### sys

| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:----------- |:----------- | ------- |
| in://local  |             |         |
| xs://config |             |         |
| xs://bucket |             |         |
| xs://secret |             |         |
| xs://cached |             |         |



### redixs

  | <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
  |:-------------- | ----------- | ------- |
  | redis://sadd   |             |         |
  | redis://sget   |             |         |
  | redis://delete |             |         |
  | redis://add    |             |         |
  | redis://get    |             |         |
  | redixs://add   |             |         |
  | redixs://get   |             |         |


### kanban

| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:--------------------- | ----------- | ------- |
| kanban://disp   |             |{"tag":kanban tag,"kanban":[{"name":item name,"data":{}} ] }       |
| kanban://create |             |{"tag":kanban tag}         |
| kanban://clear  |             |{"tag":kanban tag}       |
| kanban://delete |             |{"tag":kanban tag}        |   

### UC

| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:---------- | ----------- | ------- |
| uc://login |             |         |



### MUSTME

| <div style="width: 150pt">topic | <div style="width: 230pt">description | <div style="width: 100pt">payload |
|:---------- | ----------- |:-------|
| blog://mms |             |         |


