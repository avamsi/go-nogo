```yaml
on: [push, pull_request]
permissions: read-all

jobs:
  ci:
    uses: avamsi/go-nogo/.github/workflows/ci.yml@main
    with:
      runs-on: ubuntu-latest
```
