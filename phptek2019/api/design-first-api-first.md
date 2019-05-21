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
    


Audience questions:
* /users/123/posts vs /posts?user_id=123 - do you want to have multiple? Is that good? Bad?
    * Come to URI/hypermedia talks, but in short, there are ways to hint at the canonical path, e.g. by redirecting
