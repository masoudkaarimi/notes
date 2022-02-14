# HyperText Transfer Protocol (HTTP)

HTTP, in full HyperText Transfer Protocol, standard application-level protocol used for exchanging files on the World
Wide Web.

HTTP runs on top of the TCP/IP protocol and (later) on the QUIC protocol. Web browsers are HTTP clients that send file
requests to Web servers, which in turn handle the requests via an HTTP service

# Table of contents

- [HTTP methods](#http-methods)
  - [1xx information](#1xx-information) 
  - [2xx: Successful](#2xx-successful) 
  - [3xx: Redirection](#3xx-redirection) 
  - [4xx: Client Error](#4xx-client-error) 
  - [5xx: Server Error](#1xx-information) 
- [HTTP status code](#http-status-code-and-messages)
  - [GET](#the-get-method)
  - [POST](#the-post-method)
  - [PUT](#the-put-method)
  - [HEAD](#the-head-method)
  - [DELETE](#the-delete-method)
  - [PATCH](#the-patch-method)
  - [OPTIONS](#the-options-method)


## HTTP methods

### The GET Method

- GET is used to request data from a specified resource.
- GET is one of the most common HTTP methods.
- Note that the query string (name/value pairs) is sent in the URL of a GET request:

Example - `/test/demo_form.php?name1=value1&name2=value2`

- Some other notes on GET requests:
    - GET requests can be cached
    - GET requests remain in the browser history
    - GET requests can be bookmarked
    - GET requests should never be used when dealing with sensitive data
    - GET requests have length restrictions
    - GET requests are only used to request data (not modify)

### The POST Method

- POST is used to send data to a server to create/update a resource.
- The data sent to the server with POST is stored in the request body of the HTTP request:

  Example - `POST /test/demo_form.php HTTP/1.1` `Host: w3schools.com`  `name1=value1&name2=value2`

- Some other notes on POST requests:
    - POST requests are never cached
    - POST requests do not remain in the browser history
    - POST requests cannot be bookmarked
    - POST requests have no restrictions on data length

### The PUT Method

- PUT is used to send data to a server to create/update a resource.

- The difference between POST and PUT is that PUT requests are idempotent. That is, calling the same PUT request
  multiple times will always produce the same result. In contrast, calling a POST request repeatedly have side effects
  of creating the same resource multiple times.

### The HEAD Method

- HEAD is almost identical to GET, but without the response body.
- In other words, if GET /users returns a list of users, then HEAD /users will make the same request but will not return
  the list of users.
- HEAD requests are useful for checking what a GET request will return before actually making a GET request - like
  before downloading a large file or response body.

### The DELETE Method

- The DELETE method deletes the specified resource.

### The OPTIONS Method

- The OPTIONS method describes the communication options for the target resource.

## HTTP status code and messages

* 1xx: Information
    - 100 Continue
    - 101 Switching Protocols
    - 103 Checkpoint

* 2xx: Successful
    - 200 OK
    - 201 Created
    - 202 Accepted
    - 203 Non-Authoritative Information
    - 204 No Content
    - 205 Reset Content
    - 206 Partial Content

* 3xx: Redirection
    - 300 Multiple Choices
    - 301 Moved Permanently
    - 302 Found
    - 303 See Other
    - 304 Not Modified
    - 306 Switch Proxy
    - 307 Temporary Redirect
    - 308 Resume Incomplete

* 4xx: Client Error
    - 400 Bad Request
    - 401 Unauthorized
    - 402 Payment Required
    - 403 Forbidden
    - 404 Not Found
    - 405 Method Not Allowed
    - 406 Not Acceptable
    - 407 Proxy Authentication Required
    - 408 Request Timeout
    - 409 Conflict
    - 410 Gone
    - 411 Length Required
    - 412 Precondition Failed
    - 413 Request Entity Too Large
    - 414 Request-URI Too Long
    - 415 Unsupported Media Type
    - 416 Requested Range Not Satisfiable
    - 417 Expectation Failed

* 5xx: Server Error
    - 500 Internal Server Error
    - 501 Not Implemented
    - 502 Bad Gateway
    - 503 Service Unavailable
    - 504 Gateway Timeout
    - 505 HTTP Version Not Supported
    - 511 Network Authentication Required

