# php-type-juggling
PHP type juggling vulnerabilities arise when loose comparison `(== or !=)` of variables is employed instead of strict comparison `(=== or !==)` in an area where the attacker can control one of the variables being compared. When PHP needs to compare a string with an integer, PHP will attempt to extract the integer from the string. So a comparison like `‘2 books’ == 2` will evaluate to `True`. If the string that is being compared does not contain an integer, then string will then be converted to a `“0”` hence `‘books’ == 0` will evaluate to `True`. Loose type comparison behavior in PHP can be exploited to allow authentication bypass.

This repository contains source code for a trivial challenge. Solve it to retrive the JWT authentication token and flag.

Login Page

![image](https://user-images.githubusercontent.com/8254755/168451505-a9630527-435a-4c42-b3c1-a914059cc9e4.png)

Bypass Authentication to retrieve flag and token

![image](https://user-images.githubusercontent.com/8254755/168451577-f9843f2c-afab-4599-8103-48341f8d8664.png)


## Deploying
Run in a docker container with docker compose
```sh
$ git clone https://github.com/bensonmacharia/php-type-juggling.git
$ cd php-type-juggling
$ docker-compose up -d
$ curl http://0.0.0.0:8088/
```

Alternatively:
```sh
$ git clone https://github.com/bensonmacharia/php-type-juggling.git
$ cd php-type-juggling
$ cp -R web /var/www/html
$ curl http://localhost/web/index.php
```

## References
> [Authentication Bypass Through PHP Type Juggling](https://bmacharia.com/php-type-juggling/)

> [Challenge Source Code](https://github.com/bensonmacharia/php-type-juggling)

> [OWASP: PHP Magic Tricks: Type Juggling](https://owasp.org/www-pdf-archive/PHPMagicTricks-TypeJuggling.pdf)

> [IppSec: PHP Type Juggling - Why === is Important - Bug Bounty Tips](https://www.youtube.com/watch?v=idC5SAsKhlE)


