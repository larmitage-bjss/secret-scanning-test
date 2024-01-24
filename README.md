# Repository for testing out and demonstrating secret scanning tools

## GitGuardian

* doesn't detect existing secrets in the repo as it's only scanning the latest commit
* When pushing directly to main:
  * errors on commit where secret is added
  * pass on subsequent commit
  * passes on change to file containing secret
  * fails on removal of secret

## Trufflehog

* only detected RSA private key in separate txt file, no other secrets
* on main
  * fail on commit adding secrets
  * pass on subsequent commit
  * passes on change to file containing secret
  * passes on removal of secret