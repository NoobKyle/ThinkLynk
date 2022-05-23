---
layout: post
title:  "REST APIs + Microservices"
date:   2020-08-21 05:10:47 +0200
permalink: "/microservices"
categories: microservices rest
---

### What are Microservices

Microservices are an architectural and organizational approach to software development where software is composed of small independent services that communicate over well-defined APIs. This makes applications easier to scale and faster to develop, enabling innovation and accelerating time-to-market for new features.

![code](/ThinkLynk/assets/microservices/1.png)

#### Overview

The app is an online market where you can buy products. The backend is made up of microservices that communicate and make the app work. If one service goes down some parts of the app will still be able to work. Docker is used to run the different containers.

#### Customer Microservice

An **express.js** server is started with cors enabled as the base of the microservice. 6 endpoints are available.

##### API

- signup - receives an email, password and phone data object and creates a new user in the database.
- login - validates a data object and logs the user in.
- address - is used to update the user's shipping address.
- profile - gets all the user's data.
- shopping-details - gets the users current cart.
- wish list - gets the current items in the users wish list.
- app-events - allows this microservice to send and receive data from other services.

![code](/ThinkLynk/assets/microservices/2.png)

##### Business Logic

The async helper functions that handle all the business logic are stored in customer-service.js and these include :

Signin, Signup, AddnewAddress, GetProfile, GetShopingDetails, GetWishList, AddToWishlist, ManageCart, ManageOrder, SubscribeEvents

![code](/ThinkLynk/assets/microservices/3.png)

##### Database

Contains files that use mongoose to connect to MongoDB. It also holds the model of the type of data that will be stored in the DB and functions that process, add and retrieve data from the DB.

![code](/ThinkLynk/assets/microservices/4.png)



#### Products Microservice

##### API

- create - add new products to the database using json objects.
- category - retrieve the product category types.
- id - retrieve a certain product that has the given id.
- ids - retrieve products with the given ids.
- wish list - add items to the wish list.
- cart - add, retrieve, delete items in the cart
- / - get all products.

![code](/ThinkLynk/assets/microservices/5.png)

##### Business Logic

The async helper functions that handle all the business logic are stored in product-service.js and these include :

GetProducts, GetProductDescription, GetProductsByCategory, GetSelectedProducts, GetProductById, GetProductPayload

![code](/ThinkLynk/assets/microservices/6.png)

##### Database

Contains files that use mongoose to connect to MongoDB. It also holds the model of the type of data that will be stored in the DB and functions that process, add and retrieve data from the DB.

![code](/ThinkLynk/assets/microservices/7.png)



#### Nginx Proxy

This proxy will be used to direct traffic to the correct microservice based on the endpoint needed. If a request has data to do with customer related stuff it will be sent to the customer microservice, if it has to do with product related stuff it will be directed to the correct service. Note that the microservice can also communicate with each other using the app-events endpoint and the proxy is only client facing.

![code](/ThinkLynk/assets/microservices/8.png)

And there you have it a microservice backend. Now a frontend application will need to be connected and the services hosted.

THE END.
