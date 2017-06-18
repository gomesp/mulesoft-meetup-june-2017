##  Microservices timeline

<hr>

### 2014 - Michael Fowler popularises the microservice term

    https://martinfowler.com/articles/microservices.html

<hr>

> service-oriented **architecture style**, composed of **losely coupled elements** that have **bounded contexts**

<hr>

> Microservices are small, autonomous services that work together.

<hr>

> [...] it's architectural style/approach to developing a single application as a suite of small services, each running in its own process and communicating with lightweight mechanisms [...]

<hr>

> [...] services are built around business capabilities and independently deployable by fully automated deployment [...]

<hr>

> Built using the UNIX philosophy, or the single responsibility principle: Do one thing only, and do it well.

<hr>

### 2015 - Sam Newman writes "Building Microservices"

![](resources/images/building-microservices-book.jpg)

<hr>

### Build a monolith first

### But know what are the strategies for breaking it apart

<hr>

### Strategy 1...
### ...

<hr>

### 2016 - The year of microservices and containers.

* How does it improve my agility? Economies of scope?

![](resources/images/containers.png)

<hr>

![](resources/images/microservices-hierarchy-of-needs.png) <!-- .element height="65%" width="65%" -->

    https://thenewstack.io/introducing-microservices-hierarchy-needs/

<hr>

### 2017 - Microservices are becoming reactive

* The monolith had to have synchronous communication
* Microservices don't really need sync for everything...
* REST was abused = tight coupling

> It is unfortunate that REST is widely considered as the default microservice communication protocol. It's important to understand that REST is mostly synchronous which makes it a very unfitting default protocol for inter-service communication.
> REST might be a reasonable option when there will only ever be a handful of services, or in situations between specific tightly coupled services. But use it sparingly, outside the regular request/respnse cycle, knowing that it is always at the expense of decoupling, system evolution, scale and availability.
