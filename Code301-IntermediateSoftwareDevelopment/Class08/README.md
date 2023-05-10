## API's

# API Design Best Practices

# What does REST stand for?
 Representational State Transfer (REST).REST is an architectural style for building distributed systems based on hypermedia. 

# REST APIs are designed around a ____.
REST APIs are designed around resources, which are any kind of object, data, or service that can be accessed by the client.

# What is an identifier of a resource? Give an example.
A resource has an identifier, which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:
https://api.grubhub.com/orders/123456
"orders" is the resource while "123456" is the identifier.

# What are the most common HTTP verbs?
The most common operations are GET, POST, PUT, PATCH, and DELETE.

# What should the URIs be based on?
URIs (Uniform Resource Identifiers) in a REST API should be based on the resources that the API provides access to.

# Give an example of a good URI.
http://localhost:5000/api/v1/users/1234

In this example, http://localhost:5000 is the base URL of the API, api is a namespace or identifier for the API, v1 is the version of the API, users is a collection of resources representing users, and 1234 is the identifier for a specific user resource with an ID of 1234.

This URI is a good example of a RESTful URI for a few reasons:

It is based on a resource, in this case, a user. The URI identifies a specific user resource that clients can interact with using HTTP methods such as GET, PUT, and DELETE.

It follows a consistent pattern that makes it easy for developers to navigate the API. The base URL, namespace, version, and resource name are separated by slashes, and the resource identifier is included at the end of the URI.

It is stable and long-lasting. Once clients start using this URI to interact with the API, they can rely on it remaining the same over time, which helps ensure the stability of their applications.

Note that in this example, the URI is pointing to a locally hosted API (localhost), and the API is listening on port 5000. This is just an example, and the actual URL and port number will depend on your specific environment and the configuration of your API.

# What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
A "chatty" web API is one that requires a large number of small, fine-grained requests to accomplish a single task. For example, an API that requires a client to make multiple requests to retrieve different pieces of information about a single resource would be considered chatty.

In general, a chatty API is considered a bad thing because it can result in poor performance and increased network overhead. Each request to the API requires a certain amount of network overhead, which can add up quickly if there are a large number of requests. This can lead to slower response times and increased latency, which can negatively impact the user experience.

# What status code does a successful GET request return?
A successful GET method typically returns HTTP status code 200 (OK). 

# What status code does an unsuccessful GET request return?
If the resource cannot be found, the method should return 404 (Not Found).

# What status code does a successful POST request return?
If a POST method creates a new resource, it returns HTTP status code 201 (Created).

# What status code does a successful DELETE request return?
If the delete operation is successful, the web server should respond with HTTP status code 204 (No Content), indicating that the process has been successfully handled, but that the response body contains no further information. 