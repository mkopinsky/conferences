# Static analysis and strict typehints

Joe Ferguson

* Phan
    * Tries to prove incorrectness rather than correctness
    * Detects PHP5/7 compatibility issues
    * Shows dead code
    * Installing:
        * `composer require --dev phan/phan`
        * `vendor/bin/phan --init --init-level=1 --init-overwrite` Level=1 will detect only the most glaring issues
    * Manually configuring:
        * 