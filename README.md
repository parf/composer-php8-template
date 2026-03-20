# PHP8/8.1 composer/packagist package template

# INSTALL / How to Use:
* `composer create-project parf/composer-php8-template` **your-project-name**
* edit `composer.json`
* run `composer install`


## Provides:
* ready to use Composer Package Template for php 8/8.1 projects
* commonly used php tools (see list below)
* default tools configurations
* useful scripts

# Provided Php-Tools
* php code linter
* [psalm](https://psalm.dev/docs/annotating_code/supported_annotations/) static code analyzer and fixer
* [php-stan](https://phpstan.org/writing-php-code/phpdocs-basics) static code analyzer
* [rector](https://github.com/rectorphp/rector/blob/main/docs/rector_rules_overview.md) code analyzer & refactoring tool
* [phpDocumentor](https://docs.phpdoc.org/3.0/guide/guides/running-phpdocumentor.html#quickstart) documentation application for PHP projects
* [php-cs-fixer](https://mlocati.github.io/php-cs-fixer-configurator/) Coding Standards Fixer
* [php-unit](https://phpunit.readthedocs.io/en/9.5/writing-tests-for-phpunit.html) Unit Testing
* [spartan-test](https://github.com/parf/spartan-test) (phpunit alternative) + automated web-test framework
* [psysh](https://developpaper.com/psysh-php-interactive-console/) - php cli shell

## Shared tools setup

This template expects a `tools` symlink that points at the shared `php-tools` `bin/` directory.

Example setup:

```bash
mkdir -p ~/src
cd ~/src
git clone https://github.com/homebase/php-tools.git
cd php-tools
./php-tools install all

cd /path/to/your-project
ln -s ~/src/php-tools/bin tools
```

See [setup-tools.howto](setup-tools.howto) for the full notes.

# Scripts
> `composer test`<br>
    run [unit tests](https://github.com/parf/spartan-test). use `test-q` to run tests silently (show errors only)

> `composer psalm`<br>
    check code with [psalm](https://psalm.dev/docs/annotating_code/supported_annotations/)

> `composer stan`<br>
    check code with [php-stan](https://phpstan.org/writing-php-code/phpdocs-basics) (default level is 6)

> `composer lint`<br>
    php syntax check

> `composer psalm-dry` / `composer psalm-fix`  (aka [psalter](https://psalm.dev/docs/manipulating_code/fixing/))<br>
    review/apply suggested code changes by psalm, be careful always do *dry-run* first

> `composer cs-dry` / `composer cs-fix`<br>
    review/apply suggested code changes by [php-cs-fixer](https://mlocati.github.io/php-cs-fixer-configurator/), be careful always do *dry-run* first

> `composer doc`<br>
    generate [phpDocumentor](https://docs.phpdoc.org/3.0/guide/guides/running-phpdocumentor.html#quickstart) documentation in `doc` folder

> `./check`<br>
    do all checks: lint, unit tests, psalm, php-stan; stops when any of them failed

> `./check-commit`, `./check-push`<br>
    do `./check`, add all new files to git, do `git commit -v -s` and `git push --tags`

> `./psysh` [php cli shell](https://developpaper.com/psysh-php-interactive-console/)<br>
    <small>notable commands: `wtf`, `doc Class`, `doc Class::method`, `show Class::method`, `ls -l ClassName`, `help`</small>

see [composer.json](./composer.json) scripts section for more scripts shortcuts
