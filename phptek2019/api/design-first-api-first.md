# Design First is Better Than API First
Lorna  from Nexmo


* Start with the user story.
* UX informs API decisions
    * Formats: Enterprisey languages work well with XML; if you have users with those sorts of languages you probably 
* Write decisions down
    * All stakeholders can read and understand decisions.
    * It's maddening for a coder to write documentation first, but this is how you ship fast. To iterate on a document costs very little.
* Decisions
    * Most decisions don't matter much, but BE CONSISTENT
* API Styles
    * Most are RESTful, but also consider:
        * RPC
        * Asynchronous
            * You make a request, at some point in the future it makes a request back to a URL provided 
        * Webhooks (for incoming data)
            * Registered in advance
* Data Formats
    *  Also consider input formats!
* Error behavior
    * Use [RFC 8707](https://tools.ietf.org/html/rfc7807)
    * Use consistent behavior on all endpoints
    * Status codes for success/failure
    * Data structure is predictable
* *Collaboration Tools*
* Documentation Tools
    * Best tools work with source control, quick to create, easy to deploy, painless to maintain/update
    * [Slate](https://github.com/lord/slate) is a quick markdown API documentation tool
* API Description Languages
    * (There's another talk on this tomorrow)
    * Can be used to generate documentation
    * Fire up a mock server
    * Can import collection into Postman
        * WHOA. I want to look into this.
    * Can generate outline of either API server or a client
* Best API docs
    * Include a Quickstart for API-ready individuals
    * Include detailed tutorials
    * Have detailed API reference materials
    * "Every API is someone's first API"

Audience questions:
* /users/123/posts vs /posts?user_id=123 - do you want to have multiple? Is that good? Bad?
    * Come to URI/hypermedia talks, but in short, there are ways to hint at the canonical path, e.g. by redirecting
