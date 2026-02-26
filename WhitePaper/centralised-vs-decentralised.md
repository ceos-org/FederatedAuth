# Centralised vs Decentralised

This chapter examines the trade-offs between centralised and decentralised approaches to federated authentication and authorization.


## Definitions

TBD

- Self-Sovereign Identity

- “Provenance is information about entities, activities, and people involved in producing a piece of data or thing, which can be used to form assessments about its quality, reliability or trustworthiness”. SOURCE: [W3C PROV](https://www.w3.org/TR/prov-overview/).

- “Data integrity is the opposite of data corruption. The overall intent of any data integrity technique is the same: ensure data is recorded exactly as intended”. SOURCE: [Wikipedia](https://en.wikipedia.org/wiki/Data_integrity).

- “Trust is the characteristic that one entity is willing to rely upon a second entity to execute a set of actions and/or to make set of assertions about a set of subjects and/or scopes”.  SOURCE: [OASIS](https://docs.oasis-open.org/wss-m/wss/v1.1.1/os/wss-SOAPMessageSecurity-v1.1.1-os.html).




## Integrity Provenance and Trust


The OGC Testbed-20 and OGC Testbed-21 activities included specific tasks related to Integrity, Provenance and Trust (IPT).
The Engineering Report OGC 24-033 {cite}`OGC_24-033` presents a number of IPT use cases that were explored and prototyped during the Testbed-20 activities. The objective was to propose new IPT building blocks that are aligned with existing OGC building blocks (API) and adhere to FAIR principles.  

### Decentralized identifiers

The W3C DID specification {cite}`W3C_DID` defines Decentralized identifiers (DIDs) as a new type of identifiers that enable verifiable, decentralized digital identity. A DID refers to any subject (e.g., a person, organization, thing, data model, abstract entity, etc.) as determined by the controller of the DID. In contrast to typical, federated identifiers, DIDs have been designed so that they may be decoupled from centralized registries, identity providers, and certificate authorities. 

One of the [design goals](https://www.w3.org/TR/did-core/#design-goals) of DIDs is to be system- and network-independent and enable entities to use their digital identifiers with any system that supports DIDs and DID methods.

DIDs resolve to DID Documents that contain information about the public keys that are used by consumers of Verifiable Credentials (VC) {cite}`W3C_VC` and Verifiable Presentations (VP) to verify proofs (signatures).  

`DID Resolvers` are components that perform DID resolution by taking a DID as input and produce a conforming DID document as output.  This allows for the generation of abstractions of the underlying infrastructure which may be the [European Blockchain Service Infrastructure](https://ec.europa.eu/digital-building-blocks/sites/display/EBSI/Home) EBSI {cite}`EBSI_DID`, a distributed ledger such as [Indy](https://hyperledger.github.io/indy-did-method/), or an infrastructure serving Web DIDs {cite}`WEB_DID`.


In the `EO data supply chain` scenario of the Testbed-20 IPT activities, Decentralized Identifiers (DIDs) were used for identifying organizations and EO resources (products). 

The objective of this IPT scenario was to allow downstream EO data consumers, for example a third-party 'Watermarking' process, to “trust” the data, i.e., allow verification that data consumed is from the original data provider and allow verification of the integrity of the data.

### Verifiable credentials

In addition, EO resources were described with W3C Verifiable Credentials and Verifiable Presentations.   Verifiable Credentials are a novel way to express information as metadata, claims and proofs (signatures).  The Verifiable Credentials and Presentations are cryptographically verifiable using key information related to the DID identifying the holder and/or issuer.  In the described scenario, the `claims` correspond to EO product metadata properties, i.e. JSON(-LD) encoded EO product metadata.

To protect integrity of content of external link targets, e.g. product download links, quicklook links, multibase mulithash approaches were prototyped as proposed by W3C VC 1.1 (Hashlink) and VC 2.0 (Related Resource).

Verifiable Credentials (VC) and Presentations (VP) are exchanged between (VC) issuers, holders and verifiers.  An Indy-based `Verifier` process was demonstrated to be able to verify VC retrieved from an OGC API-Records/ STAC API compliant catalogue from a `Holder` organisation.  This organisation acted as custodian of data and metadata from data providers acting as `Issuer`.


```{mermaid}
sequenceDiagram

participant v as Verifier<br>(Data Consumer)
participant h as Holder<br>(Data Custodian)
participant issuer as Issuer<br>(Data Provider)

rect rgb(125,125,125,.2)
  note over v,Registry: Onboarding organisations
    issuer -->> Registry:Register DID
    h -->> Registry:Register DID
end
h -->>  issuer: VC Request
issuer -->> issuer: Sign VC
issuer -->>  h: Signed VC
h -->> Registry: Request DID<br>Document Issuer
h -->> h: Check VC signature

rect rgb(125,125,125,.2)
  note over v,Registry: Loop [Consuming (meta)data]
    v ->> h: VP Request
    h -->> h: Include signed VC in VP
    h -->> h: Sign VP
    h -->> v: Signed VP

    v -->> Registry: Request DID Document of Holder
    v -->> Registry: Request DID Document of Issuer
    v -->> v: Check VP signatures
end
```
Figure 1 - Verification of VC and VP (OGC 24-033)


The OGC Testbed-21 included a similar task called "Data Quality for Integrity, Provenance and Trust" (DQ4IPT).
The objectives of the task were as follows:

- Explore the integration of data quality considerations into IPT frameworks in such a way that users of Earth Observation data can have confidence in the data they use for analysis.
- Develop a reference architecture that integrates data quality considerations into IPT frameworks
- Demonstrate how the reference architecture can improve confidence in Earth Observation data
 
The activity aimed to provide a standards-based approach through which data producers such as space agencies can document and communicate the quality of their data products in a way that is both human and machine readable.

The Engineering Report OGC 26-005 {cite}`OGC_26-005` presents two IPT server implementations that were prototyped during the Testbed-21 activities:

The first implementation (D101) provided an OGC API-Process implementation with a, process that stored metadata of generated products in a STAC Catalog on a Hyperledger Fabric blockchain. The proces also stored the actual data it generates on an IPFS (Interplanetary File System) giving each resource a unique CID content identifier based on a cryptographic hash. The process acts as a Verifier of Verifiable Credentials (VC) provided with the input data.  The Verifiable Credantials related to "subjects" from multiple organisations (so-called "issuers") identified by their W3C DID which resolves to a DID document as in Testbed-20.

The second implementation (D102) hosts an API-Records/STAC-API Catalogue with STAC and ISO19115-4 metadata including quality and provenance information.  The IPT framework underneath is an evolution of the implementation in Testbed-20.  IN the STAC Catalogue, each collection, granule and organisation is identified by a W3C DID identifier.   All granules havd a DID included in the metadata via the STAC Additional Identifiers extension.

The simulated environment consists of various organisations (space agencies) that self-identify by having created a resovable DID and associated DID document.  Verifiable Credentials (VC) for granules are issued by the corresponding organisations, which can be verified downstream by validating the VC using the public key information published by the corresponding organisations in their DID documents.

For examples of the various artifacts, we refer to both Engineering Reports:

- [W3C DID Document](https://docs.ogc.org/per/24-033.html#_w3c_decentralized_identifier_document_example)
- [W3C Verifiable Credential](https://docs.ogc.org/per/24-033.html#_w3c_verifiable_credentials_example)
- [W3C Verifiable Presentation](https://docs.ogc.org/per/24-033.html#_w3c_verifiable_presentations_example)

### Additional topics

Other Self-Sovereign Identity (SSI) aspects with W3C compliant VC/VP were identified as future work in the Engineering Report OGC 24-033 {cite}`OGC_24-033`:

- Integration with OpenID Connect (OIDC) and OAuth: “OpenID for VC/VP” (OID4VC, OID4VP) {cite}`OIDC_VC`.
- Decentralized Identifiers for individuals (“natural persons”), recorded in a “wallet.” In Testbed 20, EO use cases were limited to “legal persons” (DID recorded in a Registry instead of a wallet).
- Support for privacy and confidentiality via “Selective disclosure” (i.e., ability of a holder to decide what information to share, VC formatted according to a verifier’s data schema).



