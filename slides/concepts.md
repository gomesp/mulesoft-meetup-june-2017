## So, again, why microservices? 

<hr>

### Independent Deploy, Update, Scale

<hr>

### Compute resource utilisation is optimised to its requirements

<hr>

### Can be written in any language and use any data store. Optimised for the service requirements

<hr>

### Having its own datastore improves its independence and resiliency

<hr>

### Services are resilient and built 
### to tolerate external failure

| Service Consumers  | Service Publishers |
| ------------- | ------------- |
| Design for failure | Publish standard metrics |
| Expect throttling | Aggregate your logs |
| Plan to retry | Don't leak internal details |
| Cache | Backwards compatibility |

<hr>

### Time to market is fast. Built around functional full-stack teams.

<hr>

## Are microservices all fun and dreams?

* Distributed systems are hard
* You'll need to invest more in operations, deployment and monitoring
* Performance: in-process vs. intra-process communication
* Transaction safety

<hr>

## Is my organisation ready to adopt microservices?
1. Rapid provisioning <!-- .element: class="fragment fade-in" data-fragment-index="1" -->
1. Basic monitoring. MTTR > MTBF! <!-- .element: class="fragment fade-in" data-fragment-index="1" -->
1. Rapid deployment <!-- .element: class="fragment fade-in" data-fragment-index="1" -->
1. Easy to provision storage <!-- .element: class="fragment fade-in" data-fragment-index="2" -->
1. Easy access to the "edge", i.e. user state information <!-- .element: class="fragment fade-in" data-fragment-index="2" -->
1. Authentication/Authorisation <!-- .element: class="fragment fade-in" data-fragment-index="2" -->
1. Standardised RPC <!-- .element: class="fragment fade-in" data-fragment-index="2" -->

Note:
* Did you embrace the DevOps culture?
* Storage: It's easy to get the code out. Not so easy to get the database out.
* Edge: access to the user session information
* Authentication/Authorisation: how do we determine who's the user, and does it have access to?

<hr>

## Monoliths benefit from 
## economies of scope

<hr>

## Microservices benefit from 
## economies of scale
