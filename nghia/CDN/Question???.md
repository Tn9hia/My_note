**Q: when request to CDN miss => CDN request to origin (ip client or ip CDN)**
![[Pasted image 20240414165121.png]] 
A: Use [[#x]] to check see cdn ip



**Q: when using global.vncdn.vn query at VNETWORK => routing to Hongkong** 
![[Pasted image 20240416225843.png]]
Thái: default routing to Hongkong (Bảo use VPN in Japan => Hongkong )
Anh Khiêm: base on DNS routing technic (eDNS, Anycast DNS) => use Cloudflare => wrong routing
At home:
![[Pasted image 20240416231741.png]]

**Q: Does cache share between DA server?**
When origin server is down.
- Server CDN A has already cached all the content => user connect to server A => normal
- Server CDN B does not have cache => User connect to server B => fail 
=> Cache does not share between DA server ????

**Q: When CDN storage are full but it need to cache new content (contents still have time to store in CDN) => DNS will route traffic to other CDN server or it will delete content to cache more?**
