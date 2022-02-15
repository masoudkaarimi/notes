# HyperText Transfer Protocol (HTTP)

HTTP, in full HyperText Transfer Protocol, standard application-level protocol used for exchanging files on the World
Wide Web.

HTTP runs on top of the TCP/IP protocol and (later) on the QUIC protocol. Web browsers are HTTP clients that send file
requests to Web servers, which in turn handle the requests via an HTTP service

# Table of contents

- [HTTP methods](#http-methods)
    - [GET](#the-get-method)
    - [POST](#the-post-method)
    - [PUT](#the-put-method)
    - [HEAD](#the-head-method)
    - [DELETE](#the-delete-method)
    - [PATCH](#the-patch-method)
    - [OPTIONS](#the-options-method)
- [HTTP status code and messages](#http-status-code-and-messages)
    - [1xx information](#1xx-information)
    - [2xx: Successful](#2xx-successful)
    - [3xx: Redirection](#3xx-redirection)
    - [4xx: Client Error](#4xx-client-error)
    - [5xx: Server Error](#1xx-information)

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

### 1xx: Information

| Code | Message             | Description                                                                                         |
|------|---------------------|-----------------------------------------------------------------------------------------------------|
| 100  | Continue            | The server has received the request headers, and the client should proceed to send the request body |
| 101  | Switching Protocols | The requester has asked the server to switch protocols                                              |
| 103  | Checkpoint          | Used in the resumable requests proposal to resume aborted PUT or POST requests                      |

### 2xx: Successful

| Code | Message                        | Description                                                                                                                            |
|------|--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------| 
| 200  | OK                             | The request is OK (this is the standard response for successful HTTP requests)                                                         |
| 201  | Created                        | The request has been fulfilled, and a new resource is created                                                                          |
| 202  | Accepted                       | The request has been accepted for processing, but the processing has not been completed                                                |
| 203  | Non-Authoritative Information  | The request has been successfully processed, but is returning information that may be from another source                              |
| 204  | No Content                     | The request has been successfully processed, but is not returning any content                                                          |
| 205  | Reset Content                  | The request has been successfully processed, but is not returning any content, and requires that the requester reset the document view |
| 206  | Partial Content                | The server is delivering only part of the resource due to a range header sent by the client                                            |


### 3xx: Redirection

| Code | Message             | Description                                                                             |
|------|---------------------|-----------------------------------------------------------------------------------------| 
| 300  | Multiple Choices    | A link list. The user can select a link and go to that location. Maximum five addresses |
| 301  | Moved Permanently   | The requested page has moved to a new URL                                               |
| 302  | Found               | The requested page has moved temporarily to a new URL                                   |
| 303  | See Other           | The requested page can be found under a different URL                                   |
| 304  | Not Modified        | Indicates the requested page has not been modified since last requested                 |
| 306  | Switch Proxy        | No longer used                                                                          |
| 307  | Temporary Redirect  | The requested page has moved temporarily to a new URL                                   |
| 308  | Resume Incomplete   | Used in the resumable requests proposal to resume aborted PUT or POST requests          |


### 4xx: Client Error

| Code | Message                          | Description                                                                                                                                                   |
|------|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------| 
| 400  | Bad Request                      | The request cannot be fulfilled due to bad syntax                                                                                                             |
| 401  | Unauthorized                     | The request was a legal request, but the server is refusing to respond to it. For use when authentication is possible but has failed or not yet been provided |
| 402  | Payment Required                 | Reserved for future use                                                                                                                                       |
| 403  | Forbidden                        | The request was a legal request, but the server is refusing to respond to it                                                                                  |
| 404  | Not Found                        | The requested page could not be found but may be available again in the future                                                                                |
| 405  | Method Not Allowed               | A request was made of a page using a request method not supported by that page                                                                                |
| 406  | Not Acceptable                   | The server can only generate a response that is not accepted by the client                                                                                    |
| 407  | Proxy Authentication Required    | The client must first authenticate itself with the proxy                                                                                                      |
| 408  | Request Timeout                  | The server timed out waiting for the request                                                                                                                  |
| 409  | Conflict                         | The request could not be completed because of a conflict in the request                                                                                       |
| 410  | Gone                             | The requested page is no longer available                                                                                                                     |
| 411  | Length Required                  | The "Content-Length" is not defined. The server will not accept the request without it                                                                        |
| 412  | Precondition Failed              | The precondition given in the request evaluated to false by the server                                                                                        |
| 413  | Request Entity Too Large         | The server will not accept the request, because the request entity is too large                                                                               |
| 414  | Request-URI Too Long             | The server will not accept the request, because the URL is too long. Occurs when you convert a POST request to a GET request with a long query information    |
| 415  | Unsupported Media Type           | The server will not accept the request, because the media type is not supported                                                                               |
| 416  | Requested Range Not Satisfiable  | The client has asked for a portion of the file, but the server cannot supply that portion                                                                     |
| 417  | Expectation Failed               | The server cannot meet the requirements of the Expect request-header field                                                                                    |


### 5xx: Server Error

| Code  | Message                          | Description                                                                                                |
|-------|----------------------------------|------------------------------------------------------------------------------------------------------------| 
| 500   | Internal Server Error            | A generic error message, given when no more specific message is suitable                                   |
| 501   | Not Implemented                  | The server either does not recognize the request method, or it lacks the ability to fulfill the request    |
| 502   | Bad Gateway                      | The server was acting as a gateway or proxy and received an invalid response from the upstream server      |
| 503   | Service Unavailable              | The server is currently unavailable (overloaded or down)                                                   |
| 504   | Gateway Timeout                  | The server was acting as a gateway or proxy and did not receive a timely response from the upstream server |
| 505   | HTTP Version Not Supported       | The server does not support the HTTP protocol version used in the request                                  |
| 511   | Network Authentication Required  | The client needs to authenticate to gain network access                                                    |