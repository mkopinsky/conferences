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
    * Use RFC 8707
    * Use consistent behavior 


