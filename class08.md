# API Design Best Practices 

> ### What does REST stand for ?

* **Representational State Transfer (REST) as an architectural approach to designing web services.** 

* **REST is an architectural style for building distributed systems based on hypermedia.** 

* **REST is independent of any underlying protocol and is not necessarily tied to HTTP.** 

* **REST API implementations use HTTP as the application protocol, and this guide focuses on designing REST APIs for HTTP.** 

* **advantage of REST over HTTP is that it uses open standards, and does not bind the implementation of the API or the client applications to any specific implementation.** 

> ### REST APIs are designed around a ____. 

* **design around resources** 

> ### What is an identifer of a resource? Give an example.

* **is a URI that uniquely identifies that resource** 

*For example, the URI for a particular customer order might be* 

     https://adventure-works.com/orders/1 

> ### What are the most common HTTP verbs ? 

1. GIT 
2. POST
3. PUT 
4. PATCH 
5. DELETE 

> ### What should the URIs be based on ?  

* **should be based on nouns (the resource) and not verbs (the operations on the resource).** 

> ### Give an example of a good URI.

     https://adventure-works.com/orders // Good 

> ### What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing ?

* **"chatty" web APIs that expose a large number of small resources.** 

> ### What status code does a successful GET request return?

* **HTTP status code 200 (OK)**

> ### What status code does an unsuccessful GET request return?

* **HTTP 404 (Not Found).**

> ### What status code does a successful POST request return?

* **HTTP status code 201 (Created)**

> ### What status code does a successful DELETE request return? 

* **HTTP status code 204**


