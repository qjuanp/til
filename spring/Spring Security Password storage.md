Spring 5 Security requires that prehashed passwords specifies the format of each password.

YAML files requires the password to be stored within quotes `"{encoder}hash"` so it can be read properly for the YAML parser.

Common problems
- Parser error: requires `""`
- Enconding exception: requires encoder specification
---
[Spring Security documentation](https://docs.spring.io/spring-security/reference/features/authentication/password-storage.html) -> Contains a list of the encoders supported to be specified alongside with the hash