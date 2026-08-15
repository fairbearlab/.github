# fairbearlab/.github

Shared GitHub Actions workflows for fairbearlab repositories.

## `go-ci.yml` — reusable Go CI

Runs three jobs: `lint` (golangci-lint, using the caller's `.golangci.yml`), `test`
(`go vet`, `go test -race`, `go mod tidy -diff`), and `vulncheck` (`govulncheck`).
All actions are pinned to commit SHAs.

```yaml
# .github/workflows/ci.yml in a Go repo
permissions:
  contents: read
jobs:
  go:
    uses: fairbearlab/.github/.github/workflows/go-ci.yml@main
    # with:
    #   working-directory: engine   # if go.mod isn't at the repo root
    #   race: false                 # to skip -race
```
