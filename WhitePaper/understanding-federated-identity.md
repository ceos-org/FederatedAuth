# Understanding Federated Identity: Core Concepts and Protocols

This chapter covers the fundamental concepts and protocols that underpin federated identity systems.

## Essential Terminology
- **Authentication (AuthN):** The process of verifying a user's identity via a set of credentials such as username and password. It answers the question: _Who are you?_
- **Authorization (AuthZ):** The process of determining what actions or resources an authenticated user is allowed to access. It answers the question: _What are you allowed to do?_
- **Federation:** A collection of organizations that agree to interoperate under a certain rule set. It answers the question: _Who vouched for you?_
- **Identity and Access Management (IAM):**
- **IdP versus SP**: The Identity Provider (IdP) handles authentication and generates tokens providing the user's identity. The Service Provider (SP) handles authorization, validating the tokens from the IdP, and there enforces access control based on roles or permissions.
- **Single Sign-on (SSO):** 

## User Access Process
1. User Authentication: The user verifies their identiy to gain access.
2. Role Activation: The user activates necessary roles for their tasks. 
3. Access Application / Services: The user accesses application services through authorization
   
## Foundation Protocols Driving Federation

<img width="460" height="360" alt="image" src="https://github.com/user-attachments/assets/da5e7a57-3a8b-4fe8-9bdf-8e6189c77dc9" />


  - **OAuth 2.0**: Open Authorization 2.0 (OAuth 2.0) is an authorization standard that allows third-party applications to gain limited access to a user's resources without exposing their credentials.

<img width="488" height="288" alt="image" src="https://github.com/user-attachments/assets/fbc9ac54-4de4-44d7-ab55-6f7c06d9bbb5" />

  - **OIDC**: OpenID Connect (OIDC) is an identity layer built on top of OAuth 2.0 to provie authentication. It allows useres to log in using a third-party identity provider.

<img width="588" height="303" alt="image" src="https://github.com/user-attachments/assets/d042228a-c239-4af1-9602-40968d09e79a" />
  
  - **SAML**: Security Assertion Markup Language (SAML) is an open-standard XML-based data format that allows secure sharing of authentication and authorization data between different organizations or systems. It allows a user to log in once (via their organization's identity provider) and then access various partner applications or enterprise services without needing to re-enter credentials. SAML is used by both the IdPs and SPs within federated identity management setups. 


---
Used and useful references: [Protocols](https://auth0.com/docs/authenticate/protocols)
