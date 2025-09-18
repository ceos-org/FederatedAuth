# Understanding Federated Identity: Core Concepts and Protocols

This chapter covers the fundamental concepts and protocols that underpin federated identity systems.

## Essential Terminology
- **Authentication (AuthN):** The process of verifying a user's identity via a set of credentials such as username and password. It answers the question: _Who are you?_
- **Authorization (AuthZ):** The process of determining what actions or resources an authenticated user is allowed to access. It answers the question: _What are you allowed to do?_
- **Federation:** A collection of organizations that agree to interoperate under a certain rule set. It answers the question: _Who vouched for you?_
- **Identity and Access Management (IAM):**
- **IdP versus SP**: The Identity Provider (IdP) handles authentication and generates tokens providing the user's identity. The Service Provider (SP) handles authorization, validating the tokens from the IdP, and there enforces access control based on roles or permissions.
- **Single Sign-on (SSO):** 


## Foundation Protocols Driving Federation
  - **OAuth 2.0**: Open Authorization 2.0 (OAuth 2.0) is an authorization standard that allows third-party applications to gain limited access to a user's resources without exposing their credentials.
  - **OIDC**: OpenID Connect (OIDC) is an identity layer...
  - **SAML**: Security Assertion Markup Language (SAML) is an open-standard XML-based data format that allows secure sharing of authentication and authorization data between different organizations or systems. It allows a user to log in once (via their organization's identity provider) and then access various partner applications or enterprise services without needing to re-enter credentials. SAML is used by both the IdPs and SPs within federated identity management setups. 

---
Used and useful references: [Protocols](https://auth0.com/docs/authenticate/protocols)
