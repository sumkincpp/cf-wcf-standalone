# cf-wcf-standlone

## Running on CloudFoundry

Push app as defined in wcf-manifest :
```
cf push wcf -f wcf-manifest.yml
```

An it likely will fail :
```
   2018-06-29T11:34:09.05+0300 [CELL/0] OUT Starting health monitoring of container
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8080/hello/. Your process does not have access rights to this namespace (see http://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.Net.HttpListener.AddAllPrefixes()
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.Net.HttpListener.Start()
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.Channels.SharedHttpTransportManager.OnOpen()
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    --- End of inner exception stack trace ---
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.Channels.SharedHttpTransportManager.OnOpen()
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.Channels.TransportManager.Open(TransportChannelListener channelListener)
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.Channels.TransportManagerContainer.Open(SelectTransportManagersCallback selectTransportManagerCallback)
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.Channels.TransportChannelListener.OnOpen(TimeSpan timeout)
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.Channels.HttpChannelListener`1.OnOpen(TimeSpan timeout)
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.Channels.CommunicationObject.Open(TimeSpan timeout)
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.Dispatcher.ChannelDispatcher.OnOpen(TimeSpan timeout)
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.Channels.CommunicationObject.Open(TimeSpan timeout)
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.ServiceHostBase.OnOpen(TimeSpan timeout)
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.Channels.CommunicationObject.Open(TimeSpan timeout)
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at System.ServiceModel.Channels.CommunicationObject.Open()
   2018-06-29T11:34:12.01+0300 [APP/PROC/WEB/0] ERR    at SelfHost.Program.Main(String[] args) in <REDACTED>/Program.cs:line 44
   2018-06-29T11:34:12.11+0300 [APP/PROC/WEB/0] OUT Exit status 3762504530
```
