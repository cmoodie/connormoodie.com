# Webhooks
```query
children:.
```
---

#### A webhook is a reverse HTTP-based API
An HTTP-based API allows a client to request information with GET requests to specific endpoints. For example, a client might be interested in the `/is-complete` endpoint, and could issue a GET request to get the response of `TRUE` or `FALSE`.

However, in this scenario, it's likely that the client wants to know *when* the `/is-complete` endpoint turns from `FALSE` to `TRUE`, and using an API is forced to continuously poll the server until the response changes.

Instead, wouldn't it be better if the server just let the client know when the `/is-complete` endpoint turns from `FALSE` to `TRUE`? That's what webhooks do by being a reverse API -- instead of the client sending a GET request to the server, the server sends a POST request to the client.

#### Setting up a webhook
Since the server needs to send a POST request to the client, the client needs to have an HTTP endpoint that's prepared to handle the request.

The [webhook](https://github.com/adnanh/webhook) package is a very nice and lightweight way to implement this.

Then, you just need the server to send a POST request whenever required (github has built in functionality for this).

##### Testing a webhook using cURL
The `curl` command in linux can be used to send HTTP requests, and thus test the webhook:

`curl -X POST -H "Content-Type: application/json" -d "{ "your_data": "your_value" }" <your_webhook_url>`
