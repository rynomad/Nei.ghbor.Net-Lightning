Nei.ghbor.Net Lightning
=======================

Nei.ghbor.Net Lightning is to be a reference server/client library for webapps running over Ground, utilizing the Keystone Geo-Routing convention. As imagined now, Lighting has 2 parent projects.

* NDN-js: Javascript CCN implimentation, communicating to server side CCND via websocket-proxy
* P : peer to peer browser communications via WebRTC

We hope to modify NDN-js ws-proxy to function as a P 'onramp' that will connect users with nearby peers over webRTC while retaining all of NDN-js websocket subclasses on the webRTC channel, and registering prefixes automatically according to keystone conventions. Multi-hop ccn routing will still use the regular ws-proxy/ccnd until such time as NDN-js can cache and forward interests/content within the browser (preliminary research indicates that this could be achievable via IndexedDB/sessionStorage)

Lighting API Spec
=================

This is a very rough outline of a desired API for easy development of apps in the Nei.ghbor.Net family.

NDN.Listener (location)
 -- listen for new peers on onramp, and establish NDN-WebRTC connections with other users according to keystone geo-routing conventions
 
Build Interest
 -- construct an interest according to various criteria, including keystone scope
 
NDN.expressInterest (interest, callback)
 -- request content, perform function when retrieved (or when timeout)
 
construct content object (nameUri, content)
 -- input any mime-type and return a ccnb content object, appropriately timestamped, segmented, and signed

NDN.publish (contentobject)
 -- publish a content object to the network
 




