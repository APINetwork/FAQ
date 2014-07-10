# Dependency Tree

## Usage Flows

1. API Provider
  1. API Provider implements their system.
  2. API Provider creates a translation system that processes apinetwork URIs as their API.
  3. API Provider provides an authentication mechanism (if end-user authentication is needed).
  3. API Provider registers their service cluster with API Network.
  4. API Network provides a secret token to the API provider, which they can check to ensure that the calls their API receives are legitimate and that they will be paid for their use.
  4. API Provider sets a price and other metadata regarding their API.
  5. API Provider specifies a payment address at which they will receive APICoins.
2. API Consumer (Developer)
  1. API Consumer registers an App with API Network.
  2. API Consumer selects APIs used by their application.
  3. API Consumer deposits APICoins into an address owned by the APINetwork, from which to make payments.
  4. API Consumer develops their application and distributes it to end users.
3. End User
  1. End User starts API Consumer's application.
  2. Application authenticates to the APINetwork.
  3. Application performs any additional authentication which is needed by linked APIs.
  4. User performs an operation on the application which requires use of an API.
  5. Application submits the URI corresponding to its data request to the APINetwork.
  6. The APINetwork determines which API provider will be requested to service the request, and verifies that the API Consumer has sufficient APICoins to pay for the request.
    1. If the API Consumer has has insufficient funds, the request is rejected.
    2. If sufficient funds are available, the request is forwarded to the provider, and the result returned to the Application.
  7. The APINetwork periodically (daily?) sums the usage of each API and distributes APICoins to service providers.  Payments which do not far outweigh their blockchain fees should be held.

## Components Used by Flows

| Step | [API Handler](./requirements/API-Handler.md) | [Dynamic Passport Plugins](./requirements/Dynamic-Passport-Plugins.md) | [Request Router](./requirements/Request-Router.md) | [Marketplace](./requirements/Marketplace.md) | [Billing Module](./requirements/Billing-Module.md) | [Endpoint Manager](https://github.com/LDEngine/endpoint-manager) |
| :--- | :---: |:---: | :---: | :---: | :---: | :---: |
| 1.i. | | | | | | |
| 1.ii. | X | | | | | |
| 1.iii. | X | X | | | | |
| 1.iv. | | | X | | | |
| 1.v. | X | | X | | |
| 1.vi. | | |  | X | | |
| 1.vii. | | | | X | X | |
| 2.i. | | | | | | X |
| 2.ii. | | | | | | X |
| 2.iii. | | | | | X | |
| 2.iv. | | | | | | |
| 3.i. | | | | | | |
| 3.ii. | | | | | | X |
| 3.iii. | | X | | | | X |
| 3.iv. | | | | | | |
| 3.v. | | | X | | | |
| 3.vi. | | | X | | X | |
| 3.vii. | | | | | X | |

