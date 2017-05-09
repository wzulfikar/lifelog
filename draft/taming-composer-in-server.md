change package version in composer (local machine):
- open composer.json
- change version of package you want
- do `composer install`

update composer packages in server:
- do `composer update` locally
- commit the updated composer.lock
- push the commit
- do `composer install` in server


Note:
to check what installed, use `composer info`
