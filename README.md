# Finite Tinfoil Agent Runtime Canary

Public measured Tinfoil config for manually controlled Finite Chat Hermes runtime canaries.

The Docker image is built, smoke-tested, and pushed by `finitecomputer/finitechat`.
This repo only contains the public `tinfoil-config.yml` that Tinfoil measures and
releases for deployment.

## Release

```bash
gh workflow run tinfoil-release.yml -f version=v0.1.15
```

Wait for both release workflows to complete before deploying with the Tinfoil CLI.

## Runtime Endpoints

- `/healthz`: runtime readiness and agent identity status.
- `/invite`: the same invite payload shape used by the Docker canary.
