# Repository for testing out and demonstrating secret scanning tools

## GitGuardian

* doesn't detect existing secrets in the repo as it's only scanning the latest commit
* When pushing directly to main:
  * errors on commit where secret is added
  * pass on subsequent commit
  * passes on change to file containing secret
  * fails on removal of secret
  * passes on subsequent commit
* on branch:
  * fails on adding secrets
  * fails on subsequent commits including unrelated readme changes
  * fails on removal of secrets

## Trufflehog

* only detected RSA private key in separate txt file, no other secrets
* on main
  * fail on commit adding secrets
  * pass on subsequent commit
  * passes on change to file containing secret
  * passes on removal of secret
  * passes on subsequent commit
* on PR
  * did not fail on open of PR with secrets added (RSA private key)