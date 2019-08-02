# ExtDN Interoperability Testing
This repository contains files and scripts, so that ExtDN members can
share their extensions with other other members.

## New additions (via direct commit or Pull Request)
- Add your module requirements to `scripts/composer-pre-install.sh`
    - Setup of private composer repositories including API keys
- Add your module installation to `composer.json`
- Add your module to the PHPUnit files
    - `dev/tests/integration/phpunit-extdn.xml`

## Setup for Integration Testing
- Start with a fresh Magento installation
- Follow the procedure of setting up Integration Testing 
    - Empty testing database
    - Modify details of `dev/tests/integration/etc/install-config-mysql.php`
    - Perhaps create a simple testsuite to double-check that the basics are working
- Copy this `dev/` folder to your own Magento root
- Copy this `scripts/` folder to your own Magento root
- Run `scripts/composer-pre-install.sh` in your Magento root
- Install this meta-package in Magento:
    - `composer require extdn/extdn-interoperability-testing:dev-master`
    - Check that various ExtDN members have come available under `vendor/*`

Run the actual command:
```bash
cd dev/tests/integration
../../../vendor/bin/phpunit -c phpunit-extdn.xml --testsuite ExtDN
```

# End
