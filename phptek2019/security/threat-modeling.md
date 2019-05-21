# Fortifying Your Defenses with Threat Modeling

Threat modeling is a process by which potential threats ... can be identified, enumerated, and prioritized - all from a hypothetical attacker's point of view.

* What is the process?
    1. Document everything you can about your application, its use cases, and the users
    2. Map out your application - both process flows and data flows
    3. Identify system dependencies
        * List the whole stack. Application security doesn't do much if your backups on S3 are publicly exposed
