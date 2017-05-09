Findings:

- composer update takes ram too much (~350mb in 500mb ram machiine) unlike composer install (~100mb in same machine)
- composer install refers to `composer.lock` to install packages in composer.json but not yet installed in the machine
- never do `composer update` in production to avoid mismatch version
- `composer.lock` helps developers install same exact version of packages across machines
- commit `composer.lock` into version control
- when there's `composer.lock`, it means that someone already did `composer install` in that repo
