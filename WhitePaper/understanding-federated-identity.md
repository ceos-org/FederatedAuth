# Understanding Federated Identity: Core Concepts and Protocols

This chapter covers the fundamental concepts and protocols that underpin federated identity systems.

## Essential Terminology
- **Authentication (AuthN):** The process of verifying a user's identity via a set of credentials such as username and password. It answers the question: _Who are you?_
- **Authorization (AuthZ):** The process of determining what actions or resources an authenticated user is allowed to access. It answers the question: _What are you allowed to do?_
- **Federation:** A collection of organizations that agree to interoperate under a certain rule set. It answers the question: _Who vouched for you?_
- **Identity and Access Management (IAM)** refers to the framework of policies, processes, and technologies used to manage digital identities and control access to resources within an organization.
IAM ensures that the right individuals and entities have the appropriate access to technology resources at the right times, for the right reasons. IAM is crucial for:
   - Enhancing security by preventing unauthorized access.
   - Supporting compliance with regulations like GDPR.
   - Improving user experience by enabling Single Sign-On (SSO) and streamlined access to resources.

- **IdP versus SP**: The Identity Provider (IdP) handles authentication and generates tokens providing the user's identity. The Service Provider (SP) handles authorization, validating the tokens from the IdP, and there enforces access control based on roles or permissions.
- **Single Sign-on (SSO):** 

## User Access Process
1. User Authentication: The user verifies their identity, typically via an Identity Provider (IdP), to initiate access. This step is crucial in federated systems where authentication is delegated across domains.
2. Role Activation: Once authenticated, the user's roles and permissions are determined, often conveyed through protocol-specific tokens or assertions (e.g., claims in OIDC or attributes in SAML).
3. Access Application / Services: Based on the authenticated identity and activated roles, the user is authorized to access protected applications or services, with access tokens (OAuth 2.0) or assertions (SAML) facilitating secure communication.
   
## Foundation Protocols Driving Federation

Federated identity protocols like OAuth 2.0, OpenID Connect (OIDC), and SAML are designed to support and secure each step of the user access process, enabling trusted identity verification, role-based access control, and seamless service authorization across organizational boundaries.

<img width="460" height="360" alt="image" src="https://github.com/user-attachments/assets/da5e7a57-3a8b-4fe8-9bdf-8e6189c77dc9" />


  - **OAuth 2.0**: Open Authorization 2.0 (OAuth 2.0) is an authorization standard that allows third-party applications to gain limited access to a user's resources without exposing their credentials.

<img width="488" height="288" alt="image" src="https://github.com/user-attachments/assets/fbc9ac54-4de4-44d7-ab55-6f7c06d9bbb5" />

  - **OIDC**: OpenID Connect (OIDC) is an identity layer built on top of OAuth 2.0 to provie authentication. It allows useres to log in using a third-party identity provider.

<img width="588" height="303" alt="image" src="https://github.com/user-attachments/assets/d042228a-c239-4af1-9602-40968d09e79a" />
  
  - **SAML**: Security Assertion Markup Language (SAML) is an open-standard XML-based data format that allows secure sharing of authentication and authorization data between different organizations or systems. It allows a user to log in once (via their organization's identity provider) and then access various partner applications or enterprise services without needing to re-enter credentials. SAML is used by both the IdPs and SPs within federated identity management setups. 


---
Used and useful references: 

[Foundation Protocols Driving Federation](https://auth0.com/docs/authenticate/protocols)

[Data Space Support Centre - Data Sovereignty and Trust Pillar](https://dssc.eu/space/bv15e/766068339/Data+Sovereignty+and+Trust)

[European Identity Wallet Reference architecture](https://digital-strategy.ec.europa.eu/en/library/european-digital-identity-wallet-architecture-and-reference-framework)

