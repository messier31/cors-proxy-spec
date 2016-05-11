


| Version | Relase |
| ------- | ------ |
|   1.0   |  2016  |

<img src="https://raw.githubusercontent.com/messier31/cors-proxy-spec/master/cors-proxy.png" />
<h1 align="center">CORS PROXY SPEC</h1>

### What is it?

"Cross Origin Proxy" is a way how web clients (web browsers) avoid `same origin` security restrictions. `CORS Proxy` is a server side software intended resolve client requests to remote services/servers which does not handle `CORS` requests.

### Abstract

This specification describe how cross origin proxy handle client requests.


### Basic Principle

  * Proxy server can be accessed via domain name or ip address with port. For instance : `1.2.3.4:5678`
  * Proxy server must support http and https.
  * Proxy server must handle http and https requests.
  * Proxy server `v1.0 spec` must support at least GET requests.

### GET requests

Client request proxy via http(s) with params.
Example :
```
GET https://crossproxy.me/https://requested.site/url?param=value
```

 * `https://crossproxy.me/` is an address of the proxy server.
 * `https://requested.site/url?param=value` is a param (remote website url with params)

Proxy server will respond with following headers:
```
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: GET, HEAD, OPTIONS
Access-Control-Allow-Headers: Content-type
```

Proxy server gets content of requested url and returns this content to the client, with requested `Content-Type` header.

### License

MIT License,
2016 &copy; Svetlana Linuxenko
