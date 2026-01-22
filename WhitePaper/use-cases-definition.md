# Use Cases Definition

This chapter defines the specific use cases for federated authentication and authorization in Earth Observation systems.


## ESA/NASA MAAP 
<mark>Note</mark> _[SMB]: Not sure about how much detail to go into. Can include more technical details if necessary. Also this is still in development and we dont' have a complete and functioning architecture yet._

The ESA-NASA Multi-Mission Algorithm and Analysis Platform (MAAP) is a jointly developed initiative comprising two cloud-based collaborative platforms: ESA MAAP and NASA MAAP. While operated independently, both platforms share a common architecture, design, and interoperability standards. They support the BIOMASS, NISAR, and GEDI satellite missions by integrating data, algorithms, and computing resources. A federated identity management system enables users to authenticate via their respective “home” platforms while accessing services across both. A joint landing page provides unified access, and APIs facilitate coordination for identity federation and cross-platform functionality. This setup allows for bidirectional interoperability, including shared data access and processor deployment through federated identity providers and API gateways.

#### Joint Data Access Use-Cases for ESA-NASA MAAPS: 
1. ESA MAAP user accessing NASA datasets
2. NASA MAAP user accessing datasets in ESA's MAAP STAC catalog
3. Moving user data between ESA AND NASA MAAP
4. Data Accses using federated search for data discovery 

#### Joint Processor Deployment and Execution for ESA-NASA MAAPS
The user should be able to deploy and execute a processor across both platforms from their notebook environment by changing only the endpoint. This enables users to run the same processor across different datasets, in turn allowing them to then retrieve and compare the outputs from both platforms to validate consistency.

The preconditions for these cross-platform use cases is IDP Federation: 

- NASA users can login to ESA MAAP using their NASA EarthData Account (NASA IdP), while ESA users can login into the NASA MAAP with their ESA account (eo sign in / EOIAM) as shown in the images below.
- While users can log into the other MAAP with their IdP, the API gateway allows authorized access to the datasets, anlayses, processors without the user actually needing to log into the other MAAP. 

<img width="1000" height="650" alt="image" src="https://github.com/user-attachments/assets/4bc950b8-a91b-4d32-937c-907d230fa6c0" />

<img width="1000" height="350" alt="image" src="https://github.com/user-attachments/assets/a7dd75ee-e8ba-4312-9cb7-398869fa9409" />

[NASA MAAP](https://maap-project.org/)

[ESA MAAP (BIOMASS)](https://portal.maap.eo.esa.int/biomass/)

## NASA Use Case (WGISS-59) 

## DestinE 
DestinE has two federated solutions in place: 
1. Federated Identity Provider: A federated IdP generates client credentials which are passed to the DESP Admin. They configure client credentials and specific settings. The DESP login panel then shows the added IdP IAM. Federated IdPs can login into the DestinE platform without needing to create a DESP account. 
2. Federated Services: Similiar to the federated IdP, federated services generate client credentials which are passed to the Fed. Service Admin who configures client credentials and specific settings. These are then passed to the federated service login panel which shows the DESP IAM as an IdP. Examples of these services are SesamEO and other data access services of the platform like Eden, DCMS, HDA, etc. A dedicated DestinE-IAM Documentation is provided to SPs when performing the onboarding.

[DestinE Platform Onboarding Policy and Process v2.6](https://platform.destine.eu/wp-content/uploads/2024/11/DEST-SRCO-PR-2300339-Onboarding-Policy-and-Process-v2.6.pdf)

## Bilateral ESA-DLR
<mark>Note</mark> _[UR]: will be added shortly._


## SSI Decentralised


## Use Case Summary Table

| Use Case Example    | Key Technologies Applied | AuthN |AuthZ | Objectives |PoC|
| -------- | ------- | ------- |------- |------- |------- |
|     ESA/NASA MAAP     |     |  |    |   Cross-platform data retrieval, analysis, processor deployment and execution. Federated IdPs.  |   |
|NASA Use CASE (WGISS-59)  |      |     |     |     |   |
|   DestinE  |   |    |    |  Federated IdP, Federated services.  |   |
|   Bilateral ESA-DLR  |   |    |    |    |   |
|   SSI Decentralised  |   |    |    |    |   |
