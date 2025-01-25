# Application Layer Communication
```query
children:.
```
---

## Definitions
* **Application layer communication:** Communication between two different services. These services may be on the same server, or different servers -- it doesn't matter. Actually how it goes from one IP address to another is dealt with by the transport layer, usually using TCP/IP. To communicate between services on the same server, `localhost:SERVICE_PORT` is used.
* **Application layer protocol:** A protocol used to perform application layer communication.

## Protocols

### HTTP
See [[http]]#.

### gRPC
A high performance framework able to remotely call procedures on other services. It's very useful for complicated microservice-based applications, but for simple websites it's overkill. It uses HTTP/2 over TCP.

### Apache Kafka
This is used for real-time data transferring between services at high throughput and speeds. It uses a binary TCP-based protocol as its transport layer.

## API standards and guidelines
These can be implemented using any application layer protocol.

### REST
Representational State Transfer (REST) is a set of guidelines for an API. An API that follows these guidelines is said to be RESTful. The main two guidelines are that it is stateless and is a [uniform interface](https://en.wikipedia.org/wiki/REST#Uniform_interface). APIs that use HTTP as their application layer protocol are often RESTful.

### GraphQL
GraphQL is an API standard for querying graph data.
