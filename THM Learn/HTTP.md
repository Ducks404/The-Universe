Hypertext Transfer Protocol
> Set of rules used for communicating with web servers

## HTTPS
Hypertext Transfer Protocol Secure
> Secure version that ensures encryption and makes sure the web server the user is communicating with is **not** an impersonator

## URL
Uniform Resource Locator
Address of resources where to locate

Example
![[Pasted image 20240118124733.png]]

Scheme: Protocol used
User: Some services need authentication
Host/Domain: Domain name or IP Address
Port: Port
Path: File name/location
Query String: Extra bits of information
Fragment: Reference to location on the page

## Making a request
**Example Request:  

```http
GET / HTTP/1.1
Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/
```

- Get - [[HTTP#Request Methods|Request Methods]]
- / - Page to be requested
- HTTP/1.1 - http version to be used
- Always ends with blank line to tell server request has finished

**Example Response:**

```http
HTTP/1.1 200 OK
Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98

<html>
<head>
    <title>TryHackMe</title>
</head>
<body>
    Welcome To TryHackMe.com
</body>
</html>
```

### Request Methods
- #### GET - get data
- #### POST - potentially create new records
- #### PUT - change data on server
- #### DELETE - remove a record

### Status codes

| Range___ | Name | Description |
| ---- | ---- | ---- |
| 100-199            | Information Response | These are sent to tell the client the first part of their request has been accepted and they should continue sending the rest of their request. These codes are no longer very common. |
| 200-299 | Success | This range of status codes is used to tell the client their request was successful. |
| 300-399 | Redirection | These are used to redirect the client's request to another resource. This can be either to a different webpage or a different website altogether. |
| 400-499 | Client Errors | Used to inform the client that there was an error with their request. |
| 500-599 | Server Errors | This is reserved for errors happening on the server-side and usually indicate quite a major problem with the server handling the request. |

#### Common status codes

| Status Code | Description |
| ---- | ---- |
| 200 - OK | The request was completed successfully. |
| 201 - Created | A resource has been created (for example a new user or new blog post). |
| 301 - Moved Permanently | This redirects the client's browser to a new webpage or tells search engines that the page has moved somewhere else and to look there instead. |
| 302 - Found | Similar to the above permanent redirect, but as the name suggests, this is only a temporary change and it may change again in the near future. |
| 400 - Bad Request | This tells the browser that something was either wrong or missing in their request. This could sometimes be used if the web server resource that is being requested expected a certain parameter that the client didn't send. |
| 401 - Not Authorised | You are not currently allowed to view this resource until you have authorised with the web application, most commonly with a username and password. |
| 403 - Forbidden | You do not have permission to view this resource whether you are logged in or not. |
| 405 - Method Not Allowed | The resource does not allow this method request, for example, you send a GET request to the resource /create-account when it was expecting a POST request instead. |
| 404 - Page Not Found | The page/resource you requested does not exist. |
| 500 - Internal Service Error | The server has encountered some kind of error with your request that it doesn't know how to handle properly. |
| 503 - Service Unavailable | This server cannot handle your request as it's either overloaded or down for maintenance. |

### Request Headers

Host: Some web servers host multiple websites, this header indicates which one you want
User-Agent: Browser's version number
Content-Length: How much data to expect from request
Accept-Encoding: Tells server which type of compression the browser can use
[[HTTP#Cookies|Cookie]]: Extra bits of data

### Response Headers
Set-Cookie: Setting cookies
Cache-Control: How long to store in browser's cache
Content-Type: Tells client what type of data is being returned
Content-Encoding: Tells client what compression is being used


### Cookies
