# SmooHashChecker

A lightweight Bash command-line tool to generate and verify file checksums.

## Features
- Generate SHA-256 and SHA-512 hashes.
- SHA-1 and MD5 support for legacy compatibility (not recommended for security-sensitive use).
- Verify a file against a supplied reference digest.
- Verify standard SHA-256/SHA-512 checksum manifests.
- Safely handles filenames containing spaces.

## Requirements
Bash 4+ and GNU Coreutils (`sha256sum`, `sha512sum`; optionally `sha1sum`, `md5sum`). Common Linux distributions include these by default.

## Usage
```bash
chmod +x SmooHashChecker
./SmooHashChecker hash debian.iso
./SmooHashChecker hash --algorithm sha512 debian.iso
./SmooHashChecker hash file.zip "my file.iso"
./SmooHashChecker verify debian.iso YOUR_EXPECTED_SHA256_DIGEST
./SmooHashChecker verify-manifest SHA256SUMS
```

A checksum match only shows that the file matches the supplied reference value. It does not prove who created the file or that the reference is trustworthy. Verify signatures or obtain hashes from a trusted independent source when authenticity matters.

## Exit status
- `0`: success
- `1`: mismatch or a file could not be processed
- `2`: invalid arguments or missing dependency

## License
MIT. See [LICENSE](LICENSE).
