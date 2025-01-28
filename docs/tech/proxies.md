# Proxies
```query
children:.
```
---

## Analogy
The following analogy is copied and extended from [this reddit comment](https://www.reddit.com/r/programming/comments/phnwj2/a_simple_analogy_to_understand_proxy_vs_reverse/hbkkykd/):

Imagine a table of people at a pub. There's no table service, you have to order at the bar. Everyone at the table wants to place an order. They could each go up and order for themselves. But if they have a single person go up and order for everyone, there are several advantages:

1. Increased efficiency via fewer trips.
2. Maybe there are people at the table who speak a different language. The person doing the ordering can translate their order into a language the pub staff can understand.
3. Filtering of requests. Maybe there's a child at the table who wants to order six icecream sundaes. The person doing the ordering can refuse to relay their request.

That's what a proxy does. It can reduce outgoing requests through caching, it can provide a compatibility layer, and it can filter requests.

Now imagine that single customer ordering at the bar. Each chef in the kitchen could individually accept orders. But if they have a single cashier take all the requests, there are several advantages:

1. Increased efficiency for the customer due to only having to speak to the cashier.
2. Maybe some chefs speak a different language. The cashier can translate the order into a language the chef can understand.
3. Filtering of requests. Maybe the customer requests 100 burgers. The cashier can refuse to relay their request.
4. Load balancing. Maybe there are 3 chefs that make burgers. The cashier can ensure that each chef has an equal number of orders to fulfill.

That's what a reverse proxy does. It provides one entry point to the server, it can provide a compatibility layer, it can filter requests, and it can balance loads.

## Reverse Proxies for Web Servers
A reverse proxy in a web server can allow for different domain names to be sent to different webpages, even though the HTTP GET request was to the same url. See [[dns]] for more.
