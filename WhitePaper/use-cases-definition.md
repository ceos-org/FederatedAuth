# Use Cases Definition

This chapter defines the specific use cases for federated authentication and authorization in Earth Observation systems.


## ESA/NASA MAAP 

Objective: 

- Federated IdPs: NASA users can login to ESA MAAP using their NASA EarthData Account (NASA IdP), while ESA users can login into the NASA MAAP with their ESA account (eo sign in / EOIAM) as shown in the images below.

<img width="1000" height="650" alt="image" src="https://github.com/user-attachments/assets/4bc950b8-a91b-4d32-937c-907d230fa6c0" />

<img width="1000" height="350" alt="image" src="https://github.com/user-attachments/assets/a7dd75ee-e8ba-4312-9cb7-398869fa9409" />



## NASA Use Case (WGISS-59) 

## DestinE 
DestinE has two federated solutions in place: 
1. Federated Identity Provider: A federated IdP generates client credentials which are passed to the DESP Admin. They configure client credentials and specific settings. The DESP login panel then shows the added IdP IAM. 
2. Federated Services: Similiar to the federated IdP, federated services generate client credentials which are passed to the Fed. Service Admin who configures client credentials and specific settings. These are then passed to the federated service login panel which shows the DESP IAM as an IdP. Examples of these services are SesamEO and other data access services of the platform like Eden, DCMS, HDA, etc. A dedicated DestinE-IAM Documentation is provided to SPs when performing the onboarding.

[DestinE Platform Onboarding Policy and Process v2.6](https://platform.destine.eu/wp-content/uploads/2024/11/DEST-SRCO-PR-2300339-Onboarding-Policy-and-Process-v2.6.pdf)

## Bilateral ESA-DLR

## SSI Decentralised


## Use Case Summary Table

| Use Case Example    | Key Technologies Applied | AuthN |AuthZ | Objectives |PoC|
| -------- | ------- | ------- |------- |------- |------- |
|     ESA/NASA MAAP     |     |  |    |    |   |
|NASA Use CASE (WGISS-59)  |      |     |     |     |   |
|   DestinE  |   |    |    |    |   |
|   Bilateral ESA-DLR  |   |    |    |    |   |
|   SSI Decentralised  |   |    |    |    |   |
