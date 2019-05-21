# Access Control & Authorization

* 3 tiers - Authentication, Authorization, Access Control. Strong security requires all three
    * Authentication: proving a user is who they say they are
    * Authorization: proving a user is allowed to do what they are attempting to do
    * Access Control: actually enforcing authorization controls on systems or resources
* Role-based Access Control (RBAC)
    * Users can have one or more roles
    * Each role will have one or more permissions
    * Operations are restricted based on permissions 
    * [php-rbac](http://phprbac.net/) is OWASP-maintained library for PHP
        * Looks outdated, but that's because they consider it complete
* Attribute-based Access Control
    * Users can still be assigned to one or more role
    * Resources (and users) have specific attributes
        * e.g. owner, date, status
    * Users (or roles) have applied **policies** that use these attributes to allow or block access
        * e.g. users in the download_manager role can download files that they themselves uploaded
    * Policies are evaluated at request time based on current attributes
    