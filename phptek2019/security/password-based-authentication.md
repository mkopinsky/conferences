# Password-Based Authentication Strategies
Eric.Mann@vacasa.com

* Factors
    * Something you are (identity e.g. username)
    * Something you know (e.g. password, PIN)
    * Something you have (e.g. credit card chip, Fido authentication key)
* Require strong passwords, using zxcvbn or the like rather than arbitrary rules
* Strong hashing is a must
* Restrict passwords from previously breached corpuses
* [NIST Special Publication 800-63B](https://pages.nist.gov/800-63-3/sp800-63b.html)
* Use correct cost factor
* SRP ([Secure Remote Password protocol](https://en.wikipedia.org/wiki/Secure_Remote_Password_protocol)) is a way to authenticate with a server without ever sending password to the server
    * Seems a bit like Diffie-Hellman but for a password
    * node-sodium and libsodium.js for browser, so the same code can be used on server and client
    