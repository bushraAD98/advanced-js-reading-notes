

*******

# Securing Passwords :

Cryptographic hash algorithms MD5, SHA1, SHA256, SHA512, SHA-3 are general purpose hash functions, designed to calculate a digest of huge amounts of data in as short a time as possible. Hashing is the greatest way for protecting passwords and considered to be pretty safe for ensuring the integrity of data or password.

The benefit of hashing is that if someone steals the database with hashed passwords, they only make off with the hashes and not the actual plaintext passwords. But why do we always hear about passwords being cracked? There are some weaknesses in cryptographic hash algorithm that allows an attacker to calculate the original value of a hashed password, as explained below:

- Brute Force attack
- Hash Collision attack

***************

# Basic access authentication :
is a method for an HTTP user agent to provide a user name and password when making a request. In basic HTTP authentication.

The general HTTP authentication framework
RFC 7235 defines the HTTP authentication framework, which can be used by a server to challenge a client request, and by a client to provide authentication information.

The challenge and response flow works like this:

The server responds to a client with a 401 (Unauthorized) response status and provides information on how to authorize with a WWW-Authenticate response header containing at least one challenge.
A client that wants to authenticate itself with the server can then do so by including an Authorization request header with the credentials.
Usually a client will present a password prompt to the user and will then issue the request including the correct Authorization header.


## Security of basic authentication :

As the user ID and password are passed over the network as clear text (it is base64 encoded, but base64 is a reversible encoding), the basic authentication scheme is not secure. HTTPS/TLS should be used with basic authentication. Without these additional security enhancements, basic authentication should not be used to protect sensitive or valuable information.


