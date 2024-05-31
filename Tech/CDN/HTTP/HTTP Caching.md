## Two main types of caches: 
- **private caches** : a browser cache => not share with others clients. If personalized content want to store the response only in the private cache, you must specify a `private` directive in [[HTTP header#^717649|Cache-Control]].
```
Cache-Control: private
```
- **shared caches** : is located between the client and the server and can store responses that can be shared among users.
## Fresh and stale based on age
Stored HTTP responses have two states: **fresh** and **stale**.  ^164c36
- The fresh state usually indicates that the response is still valid and can be reused ^69779d
- The stale state means that the cached response has already expired.