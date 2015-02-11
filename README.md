# Apache's APR1 MD5 Hashing Algorithm in PHP

There is no way that the best way to generate Apache's apr1-md5 password hashes is from a 7-year-old comment on php.net. Only a n00b would trust a crypto algorithm from a non-security website's forum. Sadly, that is how the PHP community has accessed this algorithm, until now.

## Generate Hashes via Other Tools

### htpasswd
```bash
$ htpasswd -nmb apache apache
apache:$apr1$rOioh4Wh$bVD3DRwksETubcpEH90ww0

$ htpasswd -nmb ChangeMe1 ChangeMe1
ChangeMe1:$apr1$PVWlTz/5$SNkIVyogockgH65nMLn.W1

$ htpasswd -nmb WhiteHat101 WhiteHat101
WhiteHat101:$apr1$HIcWIbgX$G9YqNkCVGlFAN63bClpoT/
```

### openssl
```bash
$ openssl passwd -apr1 -salt rOioh4Wh apache
$apr1$rOioh4Wh$bVD3DRwksETubcpEH90ww0

$ openssl passwd -apr1 -salt PVWlTz/5 ChangeMe1
$apr1$PVWlTz/5$SNkIVyogockgH65nMLn.W1

$ openssl passwd -apr1 -salt HIcWIbgX WhiteHat101
$apr1$HIcWIbgX$G9YqNkCVGlFAN63bClpoT/
```

## Testing

```bash
composer install
vendor/bin/phpunit
```
