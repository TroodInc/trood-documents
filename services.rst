
Microservice architecture
=========================

.. contents:: The table of contents

General concepts
----------------
A microservice architecture is an approach to creating an application that involves abandoning a single, monolithic structure. That is, instead of executing all of the application's limited contexts on a server through intraprocess communications, we use several small applications, each corresponding to a limited context. And these applications run on different servers and communicate with each other over the network, for example via HTTP.
In other words, we encapsulate certain application contexts in microservices, one for each, and place the microservices themselves on different servers.


Benefits of the microservice architecture
-----------------------------------------
Microservice architecture allows us to make our products more flexible and resilient to failure, making it easier to understand, debug and change the code.

Partial deployment
~~~~~~~~~~~~~~~~~~
Microservices allow us to update the application in parts as needed.

With a single architecture, we have to redeploy the entire application, which entails much more risk.

Accessibility
~~~~~~~~~~~~~
Microservices have better availability: even if one of them fails, it does not cause the whole application to fail.