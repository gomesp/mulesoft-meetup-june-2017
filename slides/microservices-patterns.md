##  Microservices patterns

<hr> 

### Decomposition
* How to decompose an application into services?
* Business capability or subdomain?

<hr> 

### Deployment
* Multiple service instances per host
* Service instance per host
* Service instance per VM
* Service instance per Container
* Serverless deployment
* Service deployment platform

<hr> 

### Communication patterns
* Which communication mechanisms do services use to communicate with each other and their external clients?
* Messaging for asynchronous inter-service communication
* API gateway
* Backend for front-end - a separate API gateway for each kind of client

<hr> 

### Service discovery

* How does the client discover the network location of a service instance?
* Service registry - a database of service instance locations
* Client-side discovery - client queries a service registry to discover the locations of service instances
* Server-side discovery - a router (load-balancer) queries a service registry to discover the locations of service instances

<hr> 

### Reliability
* How to prevent a network or service failure from cascading to other services?
* Circuit Breaker - invoke a remote service via a proxy that fails immediately when the failure rate of the remote call exceeds a threshold

<hr> 

### And many more

    http://microservices.io/patterns/
