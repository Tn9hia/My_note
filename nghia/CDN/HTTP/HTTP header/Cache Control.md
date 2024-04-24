The **`Cache-Control`** HTTP header field holds _directives_ (instructions) — in both requests and responses — that control [[HTTP Caching|caching]] in browsers and shared caches (e.g. Proxies, CDNs).
## Syntax
- Should be lowercase
- - Multiple directives are permitted and must be comma-separated (e.g., `Cache-control: max-age=180, public`).
## Cache directives

| Request          | Response                 |
| ---------------- | ------------------------ |
| `max-age`        | `max-age`                |
| `max-stale`      | -                        |
| `min-fresh`      | -                        |
| -                | `s-maxage`               |
| `no-cache`       | `no-cache`               |
| `no-store`       | `no-store`               |
| `no-transform`   | `no-transform`           |
| `only-if-cached` | -                        |
| -                | `must-revalidate`        |
| -                | `proxy-revalidate`       |
| -                | `must-understand`        |
| -                | `private`                |
| -                | `public`                 |
| -                | `immutable`              |
| -                | `stale-while-revalidate` |
| `stale-if-error` | `stale-if-error`         |

## Vocabulary
`(HTTP) cache`
Implementation that holds requests and responses for reusing in subsequent requests. It can be either a shared cache or a private cache.

`Shared cache`
Cache that exists between the origin server and clients (e.g. Proxy, CDN). It stores a single response and reuses it with multiple users — so developers should avoid storing personalized contents to be cached in the shared cache.

`Private cache`
Cache that exists in the client. It is also called local cache or browser cache. It can store and reuse personalized content for a single user.

`Store response`
Store a response in caches when the response is cacheable. However, the cached response is not always reused as-is. (Usually, "cache" means storing a response.)

`Reuse response`
Reuse cached responses for subsequent requests.

`Revalidate response`
Ask the origin server whether or not the stored response is still fresh. Usually, the revalidation is done through a conditional request.

`Fresh response`
Indicates that the response is fresh. This usually means the response can be reused for subsequent requests, depending on request directives.

`Stale response`
Indicates that the response is a stale response. This usually means the response can't be reused as-is. Cache storage isn't required to remove stale responses immediately because revalidation could change the response from being stale to being fresh again.

`Age`
The time since a response was generated. It is a criterion for whether a response is fresh or stale.

## Directives
### Response Directives
#### `max-age`
The `max-age=N` response directive indicates that the response remains [[HTTP Caching#Fresh and stale based on age|fresh]]  until _N_ seconds after the response is generated.
```
Cache-Control: max-age=604800
```
Indicates that caches can store this response and reuse it for subsequent requests while it's [[HTTP Caching#Fresh and stale based on age|fresh]] 

Note that `max-age` is not the elapsed time since the response was received; it is the elapsed time since the response was generated on the origin server. So if the other cache(s) — on the network route taken by the response — store the response for 100 seconds (indicated using the `Age` response header field), the browser cache would deduct 100 seconds from its freshness lifetime.
```
Cache-Control: max-age=604800
Age: 100
```

#### `no-cache`
The `no-cache` response directive indicates that the response can be stored in caches, but the response must be validated with the origin server before each reuse, even when the cache is disconnected from the origin server.
```
Cache-Control: no-cache
```
If you want caches to always check for content updates while reusing stored content, `no-cache` is the directive to use. It does this by requiring caches to revalidate each request with the origin server.

Note that `no-cache` does not mean "don't cache". `no-cache` allows caches to store a response but requires them to revalidate it before reuse. If the sense of "don't cache" that you want is actually "don't store", then `no-store` is the directive to use.
#### `must-revalidate`
The `must-revalidate` response directive indicates that the response can be stored in caches and can be reused while [[HTTP Caching#Fresh and stale based on age|fresh]]. If the response becomes [[HTTP Caching#Fresh and stale based on age|stale]], it must be validated with the origin server before reuse.

Typically, `must-revalidate` is used with `max-age`.
```
Cache-Control: max-age=604800, must-revalidate
```
#### `proxy-revalidate`
The `proxy-revalidate` response directive is the equivalent of `must-revalidate`, but specifically for shared caches only.

#### `no-store`
The `no-store` response directive indicates that any caches of any kind (private or shared) should not store this response.
```
Cache-Control: no-store
```
#### `private`

The `private` response directive indicates that the response can be stored only in a private cache (e.g. local caches in browsers).
```
Cache-Control: private
```

You should add the `private` directive for user-personalized content, especially for responses received after login and for sessions managed via cookies.

If you forget to add `private` to a response with personalized content, then that response can be stored in a shared cache and end up being reused for multiple users, which can cause personal information to leak.
### Request Directives