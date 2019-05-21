# Fortifying Your Defenses with Threat Modeling

Threat modeling is a process by which potential threats ... can be identified, enumerated, and prioritized - all from a hypothetical attacker's point of view.

* What is the process?
    1. Document everything you can about your application, its use cases, and the users
    2. Map out your application - both process flows and data flows
    3. Identify system dependencies
        * List the whole stack. Application security doesn't do much if your backups on S3 are publicly exposed
        * Equifax and Apache struts
        * wordpress and PHP mailer
    4. Identify threats
        * Physical security
            * Cleaning crews
            * Bash bunny
        * Disgruntled employee
            * Is there an off-boarding process?
            * Do people have data on (or access from) personal devices?
* [STRIDE](https://en.wikipedia.org/wiki/STRIDE_(security))
    * Spoofing
        * Phishing
        * Session take over - presenting yourself as a currently authenticated user ([Firesheep](https://en.wikipedia.org/wiki/Firesheep))
        * Logging in with another user's credentials
    * Tampering
        * SQL injection
        * Malicious code injection (XSS, RCE)
