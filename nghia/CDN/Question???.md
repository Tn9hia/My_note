Q: when request to CDN miss => CDN request to origin (ip client or ip CDN)
![[Pasted image 20240414165121.png]] 
A: Use [[#x]] to check see cdn ip



Q: when using global.vncdn.vn query at VNETWORK => routing to Hongkong 
![[Pasted image 20240416225843.png]]
Thái: default routing to Hongkong (Bảo use VPN in Japan => Hongkong )
Anh Khiêm: base on DNS routing technic (eDNS, Anycast DNS) => use Cloudflare => wrong routing
At home:
![[Pasted image 20240416231741.png]]

Q: no origin request but why origin bandwith high ?????
![[Pasted image 20240416233124.png]]

Q: log CDN make confuse

