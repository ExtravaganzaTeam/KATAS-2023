# Title

Authentication and authorization

## Status

**accepted**

## Context

Authentication is the process of verifying the credentials of a user or device attempting to access a restricted system. Authorization, meanwhile, is the process of verifying whether the user or device is allowed to perform certain tasks on the given system.  

Access to the application should be restricted to authorized users only.  

The following methods are well known but not all of them are secure and perfect match for distributed applications:  
* HTTP Basic Authentication - username and password are sent base64 encoded. This method is stateless, so the client must supply the credentials with every request. It's suitable for API calls along with simple auth workflows that do not require persistent sessions.  
* HTTP Digest Authentication - the difference to Basic Auth is that the password is sent in MD5 hashed form rather than in plain text.  
* Session-based Auth (cookie-based auth) - user's state is stored on the server. It does not require the user to provide a username or a password with each request. Instead, after logging in, the server validates the credentials. If valid, it generates a session, stores it in a session store, and then sends the session ID back to the browser. The browser stores the session ID as a cookie, which gets sent anytime a request is made to the server. Session-based auth is stateful. Each time a client requests the server, the server must locate the session in memory in order to tie the session ID back to the associated user.  
* Token-Based Authenticatin - This method uses tokens to authenticate users instead of cookies. The user authenticates using valid credentials and the server returns a signed token. This token can be used for subsequent requests. The most commonly used token is JSON Web Token (JWT). Tokens don't need not be saved on the server-side. They can just be validated using their signature.  
* One Time Passwords - are commonly used as confirmation for authentication. OTPs are randomly generated codes that can be used to verify if the user is who they claim to be. Its often used after user credentials are verified for apps that leverage two-factor authentication.
* OAuth and OpenID - OAuth 2.0 and OpenID Connect (OIDC) are industry standard protocols for user authentication and authorization. OAuth 2.0 controls and delgates authorization to access a protected resource, like your web app, native app, or API service. It provides API security through scoped access tokens. OIDC extends OAuth 2.0 with user authentication and Single Sign-On (SSO) functionality. It enables you to retrieve and store authentication information about your end users. It also defines several OAuth 2.0 scopes to enable applications to access user profile information. 


## Decision

We have decided to use OpenID Connect mechanism and JWT token to support Single Sign On functionality.  

OpenID Connect (OIDC) is an authentication standard built on top of OAuth 2.0. It defines an ID token type to pair with OAuth 2.0 access and refresh tokens. OIDC also standardizes areas that OAuth 2.0 leaves up to choice, such as scopes, endpoint discovery, and the dynamic registration of clients. You can authenticate once and use the refresh token for specified period of time.  

For RESTful APIs, token-based authentication is the recommended approach since it's stateless.  

For Single-Page Applications (SPA) running in modern browsers that support Web Crypto for PKCE the recommended is authorization code flow with PKCE. The implicit flow should not be used because it lowers security.  

We recoment to use multi factor authentication mechanism. A multi-step account login process requires users to enter more information than just a password. For example, along with the password, users might be asked to enter a code sent to their email, answer a secret question, or scan a fingerprint.  

## Consequences

Every request to the application needs the JWT token be attached to HTTP header. The HTTP header has its own size restrictions so the JWT size must meet them to be transferred with HTTP request.  