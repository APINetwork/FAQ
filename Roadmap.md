# Development Roadmap

Please see the [Dependency Tree](./Dependency-Tree.md) for a description of the user flows and list of required components.  The approximate order of capabilites is as follows:

1. Version 0:
  1. Provide an implementation of the API Network which requires API Translation (Usage Flow step 1.ii.) to be performed by API Network infrastructure.  Requires:
    2. [Endpoint Manager](https://github.com/LDEngine/endpoint-manager)
  2. Add existing APIs and their documentation to http://docs.apinetwork.co/
2. Version 0.5:
  1. Add APICoin handling and distribution.  Requires:
    1. [Billing Module](./requirements/Billing-Module.md)
  2. Move API translation tasks over to API providers.  Requires:
    1. [Request Router](./requirements/Request-Router.md)
    2. [Dynamic Passport Plugins](./requirements/Dynamic-Passport-Plugins.md)
    3. [API Handler](./requirements/API-Handler.md)
  3. Expand capabilites to include POST to URI, in addition to existing GET for URI.  Modifies:
    1. [Request Router](./requirements/Request-Router.md)
    2. [API Handler](./requirements/API-Handler.md)
  2. Add initial marketplace pages (really a static price list).
2. Version 1:
  1. Expand API Network to allow API providers to register themselves as service providers.  Modifies:
    1. [Request Router](./requirements/Request-Router.md)
    2. [Billing Module](./requirements/Billing-Module.md)
  2. Allow API providers to set their prices in the marketplace.  Requires:
    1. [Marketplace](./requirements/Marketplace.md)

