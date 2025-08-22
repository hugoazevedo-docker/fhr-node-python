# golang-hdi-devcontainer

Tests:
- `000` devcontainer with this docker image: `ubuntu:22.04` works on my machine, but not on GH Codespaces
- `001` devcontainer with this docker image: `ubuntu:22.04` works on GH Codespaces (fix with the user `vscode`)

```Dockerfile
# syntax=docker/dockerfile:1
FROM demonstrationorg/dhi-k33g-golang:1.24-debian12-dev
```
