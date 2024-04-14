## Origin Server
An [[#origin_server]], like the name implies, is where the original version of your web files is located—the computer where your website is hosted.

## Caching Servers
[[#Caching_servers]] - are core components of the content delivery network. They are computers that hold copies, or cached versions, of website content retrieved from your origin server, and deliver this stored content upon request. Caching servers work as reverse proxies—important connection points placed in front of web servers that function as intermediaries for end-user requests. Reverse proxies intercept these requests, forward them to web servers, and transmit the responses back to your website’s visitors.

These servers are located at a point of presence, one of the physical data centers spread out across the world. There are two type of caching server:

## Edge Servers
[[#Edge_server]]: the main building blocks within CDN; among other duties, their role is to execute the first level of caching. The main distinctive feature of the edge servers is to be as close to the end-user as possible—thereby reducing the round-trip time between end users and the origin server.


## Shielding Servers (Mid-cache) 
[[#Mid_tier]] server about the second level of caching. They, too, function as a reverse proxy, and “cover” the origin server from being overloaded, working as an “origin’s twin” within the network—all requests from the edges go to the mid-cache instead of the origin.

## Points_Of_Presence
[[#Points_of_presence]] is a general term describing locations and geographical coverage of the network. Usually, the point of presence is a synonym for the data center where caching (whether it’s edge or shielding) servers are hosted. A multitude of PoPs distributed across the globe make up a CDN as we know it.

When describing or assessing the extent of your CDN coverage, the term “PoP” can also be used synonymously with “edge servers.”
