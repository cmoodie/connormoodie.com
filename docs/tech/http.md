# HTTP
```query
children:.
```
---

Hypertext Transfer Protocol is an application layer protocol used to transfer text. It was originally designed to transfer hypertext -- text containing hyperlinks -- but it is now the main protocol used to transfer any kind of text.

### HTTPS
HTTPS (S for Secure) is itself not a protocol, instead it is the act of using any version of HTTP with an encryption layer to make it secure. This is done using public-private key encryption and SSL certificates.

#### SSL Certificates
These are data files that state three things:
- The server's public key, which will be used to send a symmetric key to be used for encrypted data transfer from browser to server.
- The server's name, allowing the browser to ensure that the certificate is indeed for the website the browser intended to go to.
- A signature, which is created by encrypting the above two pieces of data with the private key of the signer.

The "signer" is usually a certificate authority (CA), which is an authority your browser trusts so that you can trust the certificate. A self-signed certificate is where the certificate is signed by the private key of the server itself, which is basically the server saying "I'm me cus I say I'm me" which is not very trustworthy.

You can generate CA signed certificates using [certbot](https://certbot.eff.org/instructions?ws=nginx&os=snap).

### Versions of HTTP
See [here](https://www.litespeedtech.com/http-https-http2-http3).

### HTTP request methods
HTTP defines a number of methods that can be used by a sender of an HTTP request. For example, the GET method is for retrieving data at the endpoint the HTTP request was sent to. The actual functionality of sending the requested information back must be implemented by the server.

See [here](https://en.wikipedia.org/wiki/HTTP#Request_methods) for all of the request methods for HTTP/1.1.
