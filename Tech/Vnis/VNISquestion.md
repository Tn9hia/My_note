## Client <=> CDN <=> WAF <=> Backend
#### 1. Bot detection VNETWORK is using?
owasp - CRS tunning by VNETWORK
Have 3 mode: block, pass, stimulate
Setup on domain
#### 2. How much latency increase when apply VNIS?
Client -> CDN:  route depend on location vs ISP => **max 10ms** 
CDN -> Waf: ( **6ms** for processing filter, request,... ) 
Waf tới Orign: Depend on Origin location => **21ms -23ms**
Total Client - CDN - Waf  - Origin : < **30 ms. ~~ 22ms**

#### 3. How long can I get trial VNIS?
You have 1 weeks (7 day) to trial VNIS