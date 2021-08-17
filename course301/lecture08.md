# APIs

## RESTful web API design

*A primary advantage of REST over HTTP is that it uses open standards, and does not bind the implementation of the API or the client applications to any specific implementation.*

**Here are some of the main design principles of RESTful APIs using HTTP:**

- REST APIs are designed around resources, which are any kind of object, data, or service that can be accessed by the client.

- A resource has an identifier, which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:

HTTP : [link](https://adventure-works.com/orders/1
) 
- Clients interact with a service by exchanging representations of resources. Many web APIs use JSON as the exchange format. 
REST APIs use a uniform interface, which helps to decouple the client and service implementations. For REST APIs built on HTTP, the uniform interface includes using standard HTTP verbs to perform operations on resources. The most common operations are GET, POST, PUT, PATCH, and DELETE.

- REST APIs use a stateless request model. HTTP requests should be independent and may occur in any order, so keeping transient state information between requests is not feasible. The only place where information is stored is in the resources themselves, and each request should be an atomic operation. 

- REST APIs are driven by hypermedia links that are contained in the representation. For example, the following shows a JSON representation of an order. It contains links to get or update the customer associated with the order.

`{`
    
    "orderID":3,
    "productID":2,
    "quantity":4,
    "orderValue":16.60,
    "links": [
        {"rel":"product","href":"https://adventure-works.com/customers/3", "action":"GET" },
        {"rel":"product","href":"https://adventure-works.com/customers/3", "action":"PUT" }
    ]
`}`

### Define API operations in terms of HTTP methods

*The HTTP protocol defines a number of methods that assign semantic meaning to a request. The common HTTP methods used by most RESTful web APIs are:*

- GET retrieves a representation of the resource at the specified URI. The body of the response message contains the details of the requested resource.
- POST creates a new resource at the specified URI. The body of the request message provides the details of the new resource. Note that POST can also be used to trigger operations that don't actually create resources.
- PUT either creates or replaces the resource at the specified URI. The body of the request message specifies the resource to be created or updated.
- PATCH performs a partial update of a resource. The request body specifies the set of changes to apply to the resource.
- DELETE removes the resource at the specified URI.

### Filter and paginate data

Exposing a collection of resources through a single URI can lead to applications fetching large amounts of data when only a subset of the information is required. 

Instead, the API can allow passing a filter in the query string of the URI, such as /orders?minCost=n. The web API is then responsible for parsing and handling the minCost parameter in the query string and returning the filtered results on the server side.

## Framework vs library vs package vs module: The debate

### Module
Is the smallest piece of software. A module is a set of methods or functions ready to be used somewhere else.

### Package
Is a collection of modules. This may sound funny, but usually what a package does, is gather a number of modules holding in general the same functional purpose. 

### Library

Library is a collections of packages. It’s purpose is to offer a set of functionalities ready to use without worrying about the subsequent packages. 

### Framework
It’s a set of libraries. But this time, the framework does not just offer functionalities, but it also provides an architecture for the development work. 
