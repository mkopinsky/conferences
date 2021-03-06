# Leveraging API Specification Languages

Lorna Mitchell, Nexmo [@lornajane](https://twitter.com/lornajane)

"Writing API documentations in a way that's **so** simple that even computers can understand"
* Describe APIs in a machine-readable way
* Machine can read it and write:
    * API reference docs
    * Code SDKs
    * Postman collections
    * Mock servers
* API Spec Languages
    * OpenAPI
    * RAML (Mulesoft)
    * API Blueprint (Apiary)
* Spec-first API Design
    * Best way to build/collaborate
    * New APIs or existing ones?
        * Yes, both
* Anatomy of OpenAPI spec
    * Top-level elements
        * `openapi` - version, etc
        * `info` - often not rendered by doc builders. But take the time and fill it in. As things get indexed, we'll use this more and more. (Postman already has an index of sorts).
        * `servers`
        * `paths` - What you typically think of as API reference docs
        * `components` - Describe things here and refer to them from elsewhere in the API. Responses, field formats, etc.
        * `security` - auth (oauth, basic auth, etc.)
        * `tags`
* Editing tools
    * [Stoplight](https://stoplight.io/) is highly recommended if you like a web interface
    * Atom with `linter-swagger`
    * SwaggerUI, SwaggerHub, etc [https://swagger.io/tools/]()
    * [APICurio Studio](https://www.apicur.io/) gets good reviews
* Use version control!
* Validation tools
    * Speccy - CLI Tool with configurable rules [https://github.com/wework/speccy]()
    * Spectral - newer CLI tool, also with rules [https://github.com/stoplightio/spectral]()
    * Open API Spec Validator
    * Speccy and Spectral are both opinionated, and will throw errors for things that are technically valid