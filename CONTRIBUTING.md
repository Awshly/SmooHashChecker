# Contributing

- Keep the utility dependency-light and portable across common Linux systems.
- Quote shell variables and preserve safe filename handling.
- Prefer SHA-256 or SHA-512 for modern security-sensitive use.
- Never claim a hash authenticates a file unless the reference digest is trusted.
- Run `bash -n SmooHashChecker` and `bash tests/smoke-test.sh`.
