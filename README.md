# ASVA JS Password check

Easily check a password against OWASP ASVA v4. 2.1.1, 2.1.3, 2.1.7 / NIST 5.1.1.2 / CWE-521 requirements for minimum character count and common passwords.

2.1.1 - Minimum character count 12 and top common passwords.

2.1.3 - Passwords CAN contain spaces. Multiple consecutive spaces are truncated to single spaces

2.1.7 - Password is checked against top 10.000 most common passwords sourced from https://github.com/danielmiessler/SecLists/tree/master/Passwords/Common-Credentials
(commit a3416ba on May 27)

## OWASP ASVA
https://owasp.org/www-project-application-security-verification-standard/ (v4.0.1 is the latest as of this package release)

## NIST
https://pages.nist.gov/800-63-3/sp800-63b.html

## CWE
https://cwe.mitre.org/data/definitions/521.html

## Install

`npm i @marcusfernstrom/asva-password`

## Use

Pass a string to check and get back a map.

```
const passwordCheck = require('@marcusfernstrom/asva-password')
const result = passwordCheck('sunshine')

{ passed: false, tooShort: true, tooCommon: true }
```

```
const passwordCheck = require('@marcusfernstrom/asva-password')
const result = passwordCheck('passwordsarecool')

{ passed: true }
```
