To protect our systems they are simply without network connection.
While this is good for security, it's extremely limiting on educational information.

# Guardian
Is a "gatekeeper" that stand between our compute nodes and the World Wide Web. It work similar to a HTTP API, but filters traffic based on rules. In some sense it's not very unlike BGP routing in an extremely simplified version.

Users are forced to connect through **Guardian** as the only network connected node. Where connection method is strictly forced.
We can ensure a safe use of the World Wide Web.

## Usage
``` 
POST guard: url
```

Guardian is in a **strict filter** mode by default, this means that the way *URLs* are written determines if the request is blocked or not.

``` 
[http/https] :// [TLD] / [Resoure]
```
Guardian expect an ending forward slash ("/") on ending TLD, otherwise the request will fail. 
**Note:** Although a specific Domain is accepted, does not automaticly make all resources on the Domain accepted by **Guardian**.

## Request Routing
Guardian follow a three-step request route. 1). Check Whitelist, 2). Get Response Code, 3). Make Request.

``` 
Whitelist
```
``` 
Response Code
```
``` 
Request
```

## Limitations
Guardian cannot pass along authentication for security reasons. Some websites/API's might also block the request sent by Guardian.

## Guardian Request
When Guardian send a HTTP Request it will always identify itself with the user agent (unless otherwise is required) "Guardian (https://kidsdohpc.org/)".

## Known Issues

On some requests Guardian may return an empty response. 
