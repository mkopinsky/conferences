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
* [STRIDE](https://en.wikipedia.org/wiki/STRIDE_(security)
    * Spoofing
        * Phishing
        * Session take over - presenting yourself as a currently authenticated user ([Firesheep](https://en.wikipedia.org/wiki/Firesheep))
        * Logging in with another user's credentials
    * Tampering
        * SQL injection
        * Malicious code injection (XSS, RCE)
    * Repudiation: Make it hard to find evidence 
        * Log saturation interferes with ability so find bad behavior
            * Spam an error that throws stack traces in logs
        * Log disabling
            * Jewelry thief who steals video tape from camera 
        * Log manipulation
    * Information disclosure
        * Leaking sensitive data via various means
    * Denial of service
        * DDos via botnet
        * DoS via load testing tools
        * DoS via code or data deletion
            * memcached doesn't have internal auth controls, so if it's exposed to internet, attacker could delete keys preventing DoS
    * Elevation of privilege
        * Improperly implemented access control
        * GOD mode
* [DREAD](https://en.wikipedia.org/wiki/DREAD_(risk_assessment_model)
    * Damage Potential
        * What is the financial impact of the threat? (regulatory, suing, loss of revenue)
        * Potential impact on customer base?
    * Reproducibility
        * Can it be triggered in web browser, or does it require special skills?
        * Does the system have to be in a particular state for the attack to be reproduced?
        * Who would likely be able to reproduce this attack?
    * Exploitability
        * What does someone need to know to leverage the weakness?
            * Insider threat vs outsider threat
        * What skills or tools are required?
        * Who has the knowledge or skills required?
            * Nation state, script kiddie
    * Affected Users
        * Which classes of users are affected?
    * Discoverability
* Practical Illustrations
    * Add threat modeling to the definition of done
        * Aligns everyone to expectations (business owners, QA, dev, PM)
        * Ensures time needed for modeling is part of estimates
        * Ensures it is **always** done
        * Helps reinforce security mindset
    * Starting from scratch with a new application/service/feature
        * Threat model as part of design process
            * Iterative process. "As you get better you'll stop designing threats into it"
        * Revisit end result and threat model any changes during development 
    * Paying down security debt on existing apps
        * We all have some security debt
            * legacy code
            * uneven security practices
            * last minute requests
            * Insufficient threat modeling
        * Identify gaps
        * Have a plan for paying down
        * Track progress of the plan
        * Review progress at regular intervals
    * Continuous review
        