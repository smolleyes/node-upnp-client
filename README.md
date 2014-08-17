DESCRIPTION:
------------

Get a list of the upnp devices on your local network thru nodejs and return networkServices like objects
i originaly developped it to work with https://github.com/richtr/plug.play.js


Exemple:
--------

<pre>

var upnpClient = require('node-upnp-client');
var cli = new upnpClient();

//start search

cli.searchDevices();
</pre>

// listen for search terminated
<pre>
cli.on('updateUpnpDevice', function() {
	console.log('Servers'+ JSON.stringify(cli._servers))
});
</pre>

// listen for added / removed devices

<pre>
cli.on('updateUpnpDevice', function() {
	console.log('Servers'+ JSON.stringify(cli._servers))
});
</pre>

you can now access, servers/renderers/connectionManagers and avTransports lists with :

<pre>
cli._avTransports, 
cli._renderers, 
cli._connectionManagers, 
cli._servers
</pre>


Exemple of cli object after search with a server and renderer:
--------------------------------------------------------------
<pre>
upnpClient {domain: null, _events: Object, _maxListeners: 10, _client: Socket, _ssdp: SSDP…}
_avTransports: Array[2]
_client: Socket
_connectionManagers: Array[5]
_events: Object
_maxListeners: 10
_renderers: Array[2]
0: Object
_index: 0
baseUrl: "http://192.168.0.21:54243"
friendlyName: "salon"
icon: "http://192.168.0.21:54243/icons/sm.png"
id: "uuid:79773cf6-fbac-3fab-b616-337183de8cdc:urn:schemas-upnp-org:service:RenderingControl:1urn:upnp-org:serviceId:RenderingControl"
modelName: "Freebox"
name: "urn:upnp-org:serviceId:RenderingControl"
online: true
onserviceoffline: false
onserviceonline: false
type: "upnp:urn:schemas-upnp-org:service:RenderingControl:1"
udn: "uuid:79773cf6-fbac-3fab-b616-337183de8cdc"
url: "http://192.168.0.21:54243/service/RenderingControl/control"
__proto__: Object
1: Object
length: 2
__proto__: Array[0]
_servers: Array[3]
0: Object
_index: 0
baseUrl: "http://192.168.0.36:10293"
friendlyName: "Ht5streamer_smo-ubu"
icon: "http://192.168.0.36:10293/icons/icon_32.png"
id: "uuid:50252187-dd92-4267-8a19-502c576a4eca:urn:schemas-upnp-org:service:ContentDirectory:1urn:upnp-org:serviceId:ContentDirectory"
modelName: "Windows Media Connect compatible (Node upnpserver)"
name: "urn:upnp-org:serviceId:ContentDirectory"
online: true
onserviceoffline: false
onserviceonline: false
type: "upnp:urn:schemas-upnp-org:service:ContentDirectory:1"
udn: "uuid:50252187-dd92-4267-8a19-502c576a4eca"
url: "http://192.168.0.36:10293/cds/control"
__proto__: Object
1: Object
2: Object
length: 3
__proto__: Array[0]
_ssdp: SSDP
_udnList: Array[5]
domain: null
__proto__: upnpClient
</pre>

