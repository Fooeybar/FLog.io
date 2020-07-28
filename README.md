# flog.io
Logging Object For Sockets // Console And Nested Logging<br/>
<br/>
flog.io is designed for nested print logging; helpful in areas such as admin of multiple chat rooms or game servers.<br/>
The nested structure allows for the parent to log the output of its children over sockets.<br/>

Create a new log by:<br/>
---const flog=require('flog.io');<br/>
---let log=new flog.io(parameters);<br/>

Default Parameter Object:<br/>
{<br/>
name:''<br/>
,readconsole:false<br/>
,writeconsole:true<br/>
,formatting:true<br/>
,prefix:'\> '<br/>
,nametag:''<br/>
,suffix:' \> '<br/>
,logtag:'\-\-'<br/>
,errtag:'\!\!'<br/>
,warntag:'\~\~'<br/>
,testtag:'\?\?'<br/>
,emitname:'flog.io'<br/>
,save:100<br/>
,lock:false<br/>
}<br/>

To enable parent-child structure logging of multiple logs, add a child log to a parent by:<br/>
---flog.AddChild(childlog);<br/>

log.SetSocket(\_socket);<br/>
---Once connected, the log will send a test message over the socket, will attempt a Print call, and then Save will send<br/>
---all log.Print calls since instantiation.<br/>
---The log will continue to emit all log.Print messages through the socket.<br/>
---The receiving message event by default is 'flog.io'<br/>
---A lock parameter is false by default. If lock is set to 'true' the socket cannot be set again.<br/>
---To disconnect the socket, if lock is disabled, call log.SetSocket(undefined)<br/>

To enable logging of console.log:<br/>
---set '\_readconsole=true'<br/>
---The log will bind to the console.log function and print both the console output and log.Print calls.<br/>
<br/>




  
