# Status Codes Based On REST Methods 

> ### In your own words, describe what each group of status code represents: 


* 100’s = tell the client that the header part of the request has been received and the server will try to comply with a transmission demand of the client.

* 200’s = tell the client that its request was accepted.

* 300’s = tell the client that the resource they are requesting isn’t available at the expected location anymore.

* 400’s = invalid requests a client sent to a server. 

* 500’s = indicate problems with overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server. 

> ### What is a status code 202 ?

**This code tells the client that the request was valid, but its processing will finish sometime in the future.** 

> ### What is a status code 308 ?

**This is the right code if the resource will now be available at a new URL and the client should directly access it via the new URL in the future.** 

> ### What code would you use if an update didn’t return data to a client ? 

**204 No Content** 

> ### What code would you use if a resource used to exist but no longer does ?

**202 Accepted** 

> ### What is the ‘Forbidden’ status code ? 

**The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.** 

# Build A REST API With Node.js, Express, & MongoDB - Quick 

> ### Why do we need to pull our MongoDB database string out of our server and put it into our .env ?

**to deploy the application** 

> ### What is middleware ?

**pass to router portional express in the subiscriber file to get it from express** 

> ### What does app.use(express.json()) do ?

**make server accept JOSN** 

> ### What does the /:id mean in a route ?

**this url will go into the subiscriber Router** 

> ### What is the difference beween PUT and PATCH ?

* PUT request can lead to a number of outcomes. 

* PATCH is used when you want to apply a partial update to the resource.

> ### How do you make a defalut value in a schema ? 

**using the default keyword.** 

> ### What does a 500 error status code mean ? 

**Internal Server Error** 

> ### What is the difference between a status 200 and a status 201 ? 

* 200 OK - It’s the basic status code to tell the client everything went good. Since we don’t create endpoint accessible resource when creating an access token, we can use 200 as a status for that action. 

* 201 Created - The most fitting for Create operations. This code should signal backend-side resource creation and come along with a Location header that defines the most specific URL for that newly created resource. 
