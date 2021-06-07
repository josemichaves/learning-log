# Microservices

A micro-service is a collection of services that need to be:

* Highly maintainable and testable
* Loosely coupled
* Independent deployable

In fact its an application that lives outside the main application, but it can be used n whenever project you need. For example an email sender micro-service, it's a service that only know how to send emails and nothing more than that. In this case in any project that you use this micro-service, you can pass the necessary information to this micro-service and this will be send the email.

The pros of it it have more scalability, it's modular it can be used anywhere and also it's easier to distribute by smaller teams.

Normally we refer to the micro-services as an architecture, this architecture rely in that every service of the application will be using, need to be outside and accessible as a service of the app itself.

![Monolithic architecture vs Micro-service architecture](../.gitbook/assets/3581.1541934780.png)

