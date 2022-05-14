# php-type-juggling
PHP type juggling vulnerabilities arise when loose comparison `(== or !=)` of variables is employed instead of strict comparison `(=== or !==)` in an area where the attacker can control one of the variables being compared. When PHP needs to compare a string with an integer, PHP will attempt to extract the integer from the string. So a comparison like `‘2 books’ == 2` will evaluate to `True`. If the string that is being compared does not contain an integer, then string will then be converted to a `“0”` hence `‘books’ == 0` will evaluate to `True`. Loose type comparison behavior in PHP can be exploited to allow authentication bypass.

This repository contains source code for a trivial challenge. Solve it to retrive the JWT authentication token and flag.

## Deploying
You can make use of the online version without any installation requirement: URL - `https://php-type-juggling.herokuapp.com/`

Alternatively:
```sh
$ git clone https://github.com/bensonmacharia/php-type-juggling.git
$ cd php-type-juggling
$ cp -R web /var/www/html
$ curl http://localhost/web/index.php
```

## References
> [Authentication Bypass Through PHP Type Juggling](https://bmacharia.com/2022/05/14/php-type-juggling/)
> [Challenge URL] (https://php-type-juggling.herokuapp.com/)
> [Challenge Source Code] (https://github.com/bensonmacharia/php-type-juggling)
> [OWASP: PHP Magic Tricks: Type Juggling] (https://owasp.org/www-pdf-archive/PHPMagicTricks-TypeJuggling.pdf)
> [IppSec: PHP Type Juggling - Why === is Important - Bug Bounty Tips] (https://www.youtube.com/watch?v=idC5SAsKhlE)


