# Authentication: The Token API Talk
Tim Lytle

* Open APIs
    * Sometimes appropriate
    * What do you rate limit based on? Same answer as public web sites
    * Just adding API Keys (without any authorization) gives you a way to rate limit based on API key
* Basic
    * i.e. user/pass
    * OK for APIs, but...
    * Must store credentials
    * Hard to revoke, dangerous to expose
    * Conflates user's ability to log in to server with the server's ability to access
        * If user changes password, they need to simultaneously update server credentials
* Token
    * Physical metaphor: Hotel key. Carrying ID everywhere is equivalent to using credential-based auth, exchanging ID for key at front desk is equivalent to token auth. Key can be exchanged, revoked, etc.
    * Can be given to a 3rd party
    * Easy to revoke
    * A user can have multiple tokens, e.g. with different permissions.
* Token types:
    * Simple Generated (API Key)
        * Like password, usually random text
    * Signed Token (OAuth1)
        * Client has private key which it uses to sign a token, which is what gets sent along with request
        * Signatures matching means that requests are tamper-proof
    * Long-lived or short-lived (OAuth2)
        * Typically used together - refresh token (lasts longer), access token (much shorter)
        * Means that long-lived tokens aren't being sent back and forth a bunch
        * Could also be used to give the browser a short access to my API, but I don't want the browser to have access forever
            * This is what Firebase does
    * With Claims (JWT)
        * Token has access not just about identity, but about what the token is allowed to do. e.g. scope, expiration
        
I got distracted for the end of this talk. TODO: find Tim's slides and review (and possibly add to these notes)
