```yaml
on: [push, pull_request]
permissions: read-all

jobs:
  ci:
    uses: avamsi/go-nogo/.github/workflows/ci.yml@main
    with:
      runs-on: ubuntu-latest
```

Following commands are run for each module in the repo --
- go build
- go test
- go generate (and assert nothing changed)
- golangci-lint

See https://github.com/avamsi/climate/actions/runs/6254356594/attempts/3 for an example run.
