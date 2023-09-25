```yaml
on: [push, pull_request]
permissions: read-all

jobs:
  ci:
    uses: avamsi/go-nogo/.github/workflows/ci.yml@main
    with:
      runs-on: ubuntu-latest
```

Following commands are run on each module in the repo --

- golangci-lint
- (assert nothing changed on) go generate
- (assert nothing changed on) go mod tidy
- go build
- go test (which includes go vet)
- (an order of magnitude less often) go test -race
- (an order of magnitude less often) go test -count=10000

See https://github.com/avamsi/climate/actions/runs/6254356594 for an example run.
