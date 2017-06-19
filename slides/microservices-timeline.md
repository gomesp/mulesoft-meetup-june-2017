## Why microservices?

* Microservices are an answer to the challenges with monoliths. <!-- .element: class="fragment fade-in" -->
* Monoliths can be difficult to deploy. So we don't deploy very often. <!-- .element: class="fragment fade-in" -->
* Massive regression testing cycle for each software iteration. <!-- .element: class="fragment fade-in" -->
* Security risk. Monoliths have a large attack surface. <!-- .element: class="fragment fade-in" -->
* If a part of the application has strict change control, then everything must be under strict change control. <!-- .element: class="fragment fade-in" -->
* Scalability must consider the entire compute requirements. <!-- .element: class="fragment fade-in" -->
* Time-to-market is slow. <!-- .element: class="fragment fade-in" -->

Note:
* Security: "Insecure applications hidden behind firewalls make you feel secure until the breach happens..."
* Change control: "Because one part of the monolithic application and database holds sensitive data, all of it is subject to the most rigorous policies..."

<hr>

##  Microservices timeline

<hr>

### 2014 - Martin Fowler popularises the microservice term

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

### But know what are the strategies for breaking it apart <!-- .element: class="fragment fade-in" -->

### Embrace microservices incrementally <!-- .element: class="fragment fade-in" -->

<hr>

### Identify the contexts

![](resources/images/breaking-monolith-1.png)

Note:
* http://www.plantuml.com/plantuml/png/ROzB3i9028Rtd88Bz0fDVCJ4XQkc1y0HTH85Gx4kZ7Utfkqu4rtoF-23JYoEIzD7nmP1hpULZzAu6czCnTija7ayKd3SgUWb-XcVWFWDhuP0mzR7m8NU3Zl_wOiGz2wfyW8uaDEUEauNrfC0CB5XLTLrYGNvDFfp7I1Z6gqSfWJuzI4zMcoTeTu0
* Domain-driven design technique
* Powerful tool to help a team understand their business domain, the boundaries between distinct models, and how they are currently, or can be, integrated.
* A Context Map is not an Enterprise Architecture or system topology diagram.

<hr>

### New features as separate services

![](resources/images/breaking-monolith-2.png)

Note:
* Before you start: Must have CI/CD in place
* Confidence in the tests
* http://www.plantuml.com/plantuml/png/RL3B3e8m4BptA_e3_0A9G4XCn0lX0sfPjGbspLBaOFntIy3Q1uSUTcQwEpFY1jhmWd0UWPZ4nnFrWhG62Mf2RReZ4sJKLKZ36zGuA7FdRyRvNrnQGGlqKX82lBCxz_23b3Xfz-N3M2-Ck8WHt8Lg0nYJ0quzFyDSWp0JGQCauRX-ZNnOaSzQpksDgAe83PMdnSLM0y-oF0yRy8UL_XbbNlYLyLE7ILFU5HhiTE7Jit74Q5v5InpxqdExwgIQBm00
* Anticorruption Layer: A Domain Service (7) can be defined in the downstream Context for each type of Anticorruption Layer. You may also put an Anticorruption Layer behind a Repository (12) interface. If using REST, a client Domain Service implementation accesses a remote Open Host Service. Server responses produce representations as a Published Language. The downstream Anticorruption Layer translates representations into domain objects of its local Context. This is where, for example, the Collaboration Context asks the Identity and Access Context for a User-in-Moderator-role resource. It might receive the requested resource as XML or JSON, and then translates to a Moderator, which is a Value Object. The new Moderator instance reflects a concept in terms of the downstream model, not the upstream model.

<hr>

### ACL?
#### Yeah, The Anti-Corruption Layer!  <!-- .element: class="fragment fade-in" -->

Note:
* According to ACL, complete translation of the old model must be performed outside of the new service. In other words, the new microservice has its API, data formats, etc., whereas ACL adapts input provided by the monolith to the new model. 

<hr>

![](resources/images/breaking-monolith-2.png)

<hr>

### Extracting the microservices

![](resources/images/breaking-monolith-3.png) <!-- .element height="75%" width="75%" -->

Note:
* http://www.plantuml.com/plantuml/png/XL91Zi8m3Bpx5Vu0Nq1QG4WSs0lY0TdKi95Al79TM0drxwIqf4cwQ8-PcSxOuvepUSMLyAqX0SkN7_OzSb0MsWfxFUx0YBgJiOfxzbmx_SOx84xYTH0SIAxEKi1FOYw4n-0tOayrOdH9g7NjWa6WkypmmrfkVVJi02gZviiq54VOZ020hRcjy9DkMpBQ2ksT5Mv6_x00_UfpWcWHfAbciygo2xOF7nBwiTzvJv-NgZIuvE8E8MCy0IuMosNUVleOw5S7a1G_C4cra9Suv-CnCyyuqposRAPuJmd_g-OdcFqKR-nAu6_PQui7

<hr>

![](resources/images/breaking-monolith-4.png) <!-- .element height="75%" width="75%" -->

Note:
* http://www.plantuml.com/plantuml/png/TLBBRW8n3BpxA_83_08IB4Ag1BqWpbK8faHQuYgRBKWL_zuaX3ntRubdF1u_-3SgmzQQxWDg47Jx8UKY1qCQjvgKENu0rqPUk31iJufwQQxi3nYBqSw-3gX_fK0RlcX-GtQqSY7coHazWxfUsc8MVkPwAo5eL57o2N3cXf_uWD709WG0H4_ZcNtYVOlSZ1htKcWQWhorZm_Z3KG9IyqvcxK5KzyLweg_AZZNSzeflMRbXMiizX1hk44MsKdOGL-hRXUOOKGpv81wFeJTiiLYkIpNcdzUS6E_fTG3QXbJtbfMqojaPvJSl8-Wl8aMZvVfaUPCAjSptKwosdjf3dX6hWvCqwB7UY9fJdwHxqVP8KnCkrY3pytUPVe_

<hr>

![](resources/images/breaking-monolith-5.png) <!-- .element height="65%" width="65%" -->

Note:
* http://www.plantuml.com/plantuml/png/TLBRQW8n47tFL-G7_0L1Lon2BGNnMT8uje4raUnijoB-UvDip7NtRPXpvioP2_i6YNIjrT219bnTRqhQp06LXgrM4eyxmZIA2-D8zqggLk0FVH1AGxOnqG7qh-1WqXVDha2FHixd73cX9r3J2jFCmCzKRyMvwcMGV19oPiY-M0V1mCOd2E6jwi_q0uOjCEmrx0NNglFonZxyeJCG90mrvMpM1enp5wXjFdQmhkUqOtd9IXkNM9WXzB2BpAgZi8LEg-RTC_sAPiWU7Van-xaxlJ64WTq9yHUdYyLocHyxeOreDLF5A9TM4QRiLgHg-jIMrqb7IDuk6dqzJVv3DHu-sI7LMnKJpInYabN_L_NmCt9bOfeMF9RxYbjqXty5-OHauXJPZLnj4kVb_m00

<hr>

![](resources/images/breaking-monolith-6.png)

Note: 
* http://www.plantuml.com/plantuml/png/ZP9T2eCm48JVSufSm2i8_c3neQLGF40QboAqIOcnjfJUlH6LB9jO-cPsFcUIJCG5bEMvqMCFXabzksirJR9ZlHCMHl52mvFL1YgZbMrgnkHL3oq_m5Y1i8E1VIUDTYwFJaBX67XQ_cQSjyAAi-XXGZ5JvaxqvaHbdpMXSPCjR_yxfN0mrSf5y1c5C1OJfrzH5CPHL0kZCYdreFvFY_0uC2BZpALPdYHfIlh3grb7fVlFMQBjK3su4mh4Zi68wqm6JKQfy37HBMouHJQoGJ8wYNFhTNy1

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
