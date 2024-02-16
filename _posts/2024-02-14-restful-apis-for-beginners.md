---
author: Rita-Maria Oladokun
description: This post introduces the concept of REST APIs to beginners using a coffee shop analogy.
image: https://images.unsplash.com/photo-1513267048331-5611cad62e41?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTJ8fGNvZmZlZSUyMHNob3B8ZW58MHx8MHx8fDA%3D
---

# REST API For Beginners
![job hunting](https://images.unsplash.com/photo-1513267048331-5611cad62e41?w=1100&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTJ8fGNvZmZlZSUyMHNob3B8ZW58MHx8MHx8fDA%3D
)

## Introduction

Imagine owning a coffee shop. There are customers, a waitress who takes their order and a barista who prepares the cups of coffee. When the coffee is ready, he passes it to the waitress who then hands it over to the customer, thus the order is fulfilled. In developing web applications, this scenario mirrors the interaction between the frontend (customer), backend (barista), and the API (waitress), our focus here.
An API, short for Application Programming Interface, facilitates communication between two applications – the client and the server. It creates a seamless exchange where client requests are dispatched to the server, fulfilled, and a response is relayed back through the API to the client. This interaction is the request-response cycle.
Different APIs, including SOAP, RPC, Websocket, and REST, serve distinct purposes. We will take a closer look at the last one in this article

## How REST APIs work

REST stands for Representational State Transfer and it refers to an API that aligns to [REST architectural constraints](https://www.geeksforgeeks.org/rest-api-architectural-constraints/). This type of API communicates using [HTTP](https://en.wikipedia.org/wiki/HTTP) requests to execute fundamental database operations like creating, reading, updating and deleting records in a specified resource. This is also known as CRUD operations. Thinking back to our coffee shop example, when a customer places an order, the waitress (API) is receiving a POST request to create a new record for that order in the shop’s database. The barista receives and processes this request, the order record is stored in the database and he sends a response to let the waitress know it was successful. This response will contain a unique order id that the waitress hands over to the customer. The customer can retrieve all the details about his order using that order id by sending a GET request through the waitress to the barrister. The barista uses this id to search the database, retrieve the information about this order and send it back to the customer through the waitress. The order record, containing data such as customer name, title and amount paid, becomes the focal point of subsequent interactions.
> Order = {
>            id: 001,
>            customerName: “John Doe”,
>            title: “Iced Americano”,
>            amount: “1000”
>         }

The customer may choose to update his order from an Iced Americano to a Soy latte by using a PATCH/PUT request. Choosing to cancel the order will be a DELETE request.

## REST API request 
A Restful API request will contain the following:
1. **An endpoint url:** This is a specific location within the API that receives  requests and sends back responses. For example customer orders for the coffee shop can have “https://greatcoffeeshop/orders” as the endpoint.
2. **Request headers:** containing data like authentication tokens that verify users identitity and authorize access to protected resources so that not just anyone can access sensitive data.
3. **Body data:** Data within the [HTTP](https://en.wikipedia.org/wiki/HTTP) body that carries information for creating or updating a record.
4. **A HTTP method:** As mentioned earlier, this can either be GET, POST, PUT, PATCH or DELETE.

| HTTP Method | Action | CRUD Operation |
|-------|--------|---------|
| GET          | Returns data for a record | read |
| POST | Creates a new record | create |
| PUT | Updates an existing record | update |
| PATCH | Updates a part of an existing record | update |
| DELETE | Delete an existing record | delete |

**Examples**
- A POST request to “https://greatcoffeeshop/orders” creates a new order with a unique ID (eg 001) using data in the request body.
- A GET request to “https://greatcoffeeshop/orders” returns all the orders for the coffee shop
- A GET request to “https://greatcoffeeshop/orders/001” returns the order with unique ID 001
- A PUT/PATCH request to “https://greatcoffeeshop/orders/001” updates the order with unique ID 001 using the body data
- A DELETE request to “https://greatcoffeeshop/orders/001” deletes the order with unique ID 001

## REST API Response
A Restful API response will contain the following:
1. **HTTP status code:** A message the server sends to describe whether a request can be completed or not
   - 200 - OK (the request was successful)
   - 201 - Created (A record was created successfully)
   - 400 - Bad request (The request was not sent correctly, eg a wrong ID was sent)
   - 500 - Server error (The server responded with an error)
   - 404 - Not found (The resource or record cannot be found)
   - 403 - Forbidden (The request headers does not have the required authorization eg a customer is trying to retrieve an order that is not theirs)
   - 401 - Unauthorized (User sending the request is unauthenticated. This means the user needs to login first before they can send the request) 
2. **Response data:** This is the data sent back from the server. Eg POST request to https://greatcoffeeshop/orders/001 can return the customer name and title of the order.

## REST API Best Practices
1. **Use nouns for resource naming rather than verbs:**
     - https://greatcoffeeshop/orders - correct
     - https://greatcoffeeshop/ordering - wrong
2. **Have a consistent endpoint url structure:** Consistency across your API is important to make it easier to understand and navigate, like using plural nouns ("/orders" instead of "/order") and avoiding unnecessary nesting (use "/orders/001" instead of "/orders/id/001")
3. **Authentication:** For APIs that allow access to private data, permit updates and deletes, requests should be validated to ensure that the user is logged in and has the appropriate permissions. This can be done by passing an encoded string to the HTTP request authorization header whenever the user logs in). 

## Conclusion
In essence, REST APIs are a HTTP-driven mechanism for efficient client-server communications, mirroring a well-choreographed coffee shop order fulfillment system. They are fast, lightweight, highly scalable, secure, and easy to use. 
