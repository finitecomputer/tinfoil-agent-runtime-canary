# Finite Tinfoil Agent Runtime Canary

Public measured Tinfoil config for manually controlled Finite agent runtime canaries.

The Docker image is built and pushed by `finitecomputer/finitecomputer`. This repo only contains the public `tinfoil-config.yml` that Tinfoil measures and releases for attestation.

## Release

```bash
gh workflow run tinfoil-release.yml -f version=v0.1.0
```

Wait for both release workflows to complete before deploying with the Tinfoil CLI.

## Runtime Endpoints

- `/health`: public healthcheck.
- `/status`: public non-secret status and agent `npub` when available.
- `/finitechat-invite`: requires `Authorization: Bearer $FINITE_RUNTIME_STATUS_TOKEN`.
  Returns the stable Finite Chat invite URL/code plus the current challenge PIN.
  Repeating the request after the PIN window advances should keep the invite URL
  stable and return a new PIN.
