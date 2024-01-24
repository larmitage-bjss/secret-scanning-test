# Repository for testing out and demonstrating secret scanning tools

## GitGuardian

* doesn't detect existing secrets in the repo as it's only scanning the latest commit
* When pushing directly to main, errors only on the commit adding secrets
  * errors on commit where secret is added