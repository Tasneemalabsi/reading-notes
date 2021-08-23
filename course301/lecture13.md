# CRUD

## CRUD (Create, Read, Update, Delete)

*The CRUD model defines the most basic API actions for persistent storage. Create, read, update, and delete.*

### CREATE
*The create action is usually implemented via HTTPs POST method. In RESTful APIs, these endpoints are used to create new resources or access tokens.*

**Status Codes**

- 200 OK - It’s the basic status code to tell the client everything went good. 
- 201 Created - The most fitting for Create operations. This code should signal backend-side resource creation and come along with a Location header that defines the most specific URL for that newly created resource.
- 202 Accepted - Often used for asynchronous processing. This code tells the client that the request was valid, but its processing will finish sometime in the future.
- 303 See Other - Like the 202 code but using a Location header field in response to informing the client about the location of the created resource or an endpoint that lets the client check for the status of the creation process. 

**READPermalink**

*The read action gets implemented via HTTPs GET method and used to fetch resource representations. Asynchronous responses aren’t much of a thing here, because the reason for asynchronous processing is often that the resource doesn’t exist yet and has to be created, so it’s a create action anyway.*

**Status Codes**

- 200 OK - Most of the read actions will be answered with a 200 OK status.
- 206 Partial Content - This code is useful for lists of content that are too big to be delivered in one response. It has to be used with a Range header field in the request. 
- 300 Multiple Choices - This redirect is used if there are multiple representations for one resource and the client (or its user) has to choose one of them.
- 308 Permanent Redirect - This tells the client to use another URL to access the resource and not use the current URL anymore. 
- 304 Not Modified - Is used like 200 but without a body, so the client will be redirected to its locally cached representation from a previous read.
- 307 Temporary Redirect - When the URL to a resource could change in the future, and the client should always ask the current URL before accessing the real one.

### UPDATE

*An update can be implemented with an HTTP PUT or PATCH method. The difference lies in the amount of data the client has to send to the backend.*

***PUT** requires the client to send an entire representation of a resource to update it. (Replace the old one with the new one)*

***PATCH** requires the client only send parts of the representation of the resource to update it. (Add, update or delete these parts in the old version)*

**Status Codes**

- 200 OK - This is the most appropriate code for most use-cases.
- 204 No Content - A proper code for updates that don’t return data to the client, for example when just saving a currently edited document.
- 202 Accepted - If the update is done asynchronous, this code can be used. It should include an URL to access the updated resource or an URL to check if the update has been succeeded. 

### DELETE

*The delete action can be implemented with the HTTP DELETE method.*

**Status Codes**

- 200 OK - Some people think a delete function of any kind should return the deleted element, so a representation of the deleted element can be included in the response body.
- 204 No Content - The most fitting status code for this case. 
- 202 Accepted - If the deletion is asynchronous and takes some time, which is the case in distributed systems, it can be appropriate to return this code with some information or URL to tell the client when it will be deleted.

## API Changes

*If our API lives long enough, sooner or later it will change its structure.*

**Status Codes**

- 307 Temporary Redirect - This is the right code if the resource could be available on a different URL in the future.
- 308 Permanent Redirect - This is the right code if the resource will now be available at a new URL and the client should directly access it via the new URL in the future. The current endpoint can’t control the clients’ behavior after the request and a subsequent redirect if the resource URL changes again have to be issued from the new URL.

## Errors

- Many API frameworks use 500 and 404 status codes by default when something went wrong, but depending on the situation, often there are more descriptive ones.

- 500 means Internal Server Error, which can be anything from a missing header field the backend accessed without checking its existence to an unreachable third party service the backend wanted to call.

- 404 means Not Found. This can be because of a wrong URL used by the client to some endpoint not being set up right on the backend.

### Wrong URL
*When a client sends a URL, we don’t know. This can have multiple different reasons, so we have to check which of them applies here.*

**Status Codes**

- 404 Not Found - This is the most natural of responses and should be used in the case that the client URL was wrong.
- 405 Method Not Allowed - In many frameworks we define the URL alongside the HTTP method, so removing one of these definitions could leave all but one methods to one URL intact.
- 501 Not Implemented - Like 405, but the method is missing for all resources on the backend.
- 406 Not Acceptable - The URL exists, but the backend can’t send a representation the client will accept.
- 410 Gone - This is like 404 but we know that the resource existed in the past, but it got deleted or somehow moved, and we don’t know where.
- 414 Request-URI Too Long - This is sometimes the case when the endpoint is right, and the resource exists, but the query makes the URL too long to be interpreted.
- 308 Permanent Redirect - This would be the right code if we know that a resource has moved to a different URL and we can tell the client about it.
- 307 Temporary Redirect - Same as 308, but we don’t know if the resource will be back on the original URL or another different URL in the future.

### No Permissions

*Often clients can’t access every resource on the backend, so we need a way to tell them about it.*

**Status Codes**

- 401 Unauthorized - The client hasn’t authorized itself to the backend yet and the server may give it access after that has happened.
- 403 Forbidden - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.
- 404 Not Found - If 401 or 403 is the case, but the backend doesn’t want to tell the client that the resource exists for security reasons.

