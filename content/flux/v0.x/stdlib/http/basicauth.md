---
title: http.basicAuth() function
description: >
  The `http.basicAuth()` function returns a Base64-encoded basic authentication
  header using a specified username and password combination.
aliases:
  - /influxdb/v2.0/reference/flux/functions/http/basicauth/
  - /influxdb/v2.0/reference/flux/stdlib/http/basicauth/
  - /influxdb/cloud/reference/flux/stdlib/http/basicauth/
menu:
  flux_0_x_ref:
    name: http.basicAuth
    parent: http
weight: 202
introduced: 0.44.0
---

The `http.basicAuth()` function returns a Base64-encoded basic authentication
header using a specified username and password combination.

```js
import "http"

http.basicAuth(u: "username", p: "passw0rd")

// Returns "Basic dXNlcm5hbWU6cGFzc3cwcmQ="
```

## Parameters

### u {data-type="string"}
The username to use in the basic authentication header.

### p {data-type="string"}
The password to use in the basic authentication header.

## Examples

##### Set a basic authentication header in an HTTP POST request
```js
import "monitor"
import "http"

username = "myawesomeuser"
password = "mySupErSecRetPasSW0rD"

http.post(
    url: "http://myawesomesite.com/api/",
    headers: {Authorization: http.basicAuth(u:username, p:password)},
    data: bytes(v: "something I want to send."),
)
```
