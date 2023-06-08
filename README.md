tocenbough: prevent accumulating too many unreleased changes
====

tocenbough counts the number of merge commits since the latest release.
Whenever the number of merge commits exceeds the specified threshold, this action fails.

```
name: tocenbough
on:
  pull_request:
    types: [opened, reopened, labeled, unlabeled, synchronize]
jobs:
  cd:
    runs-on: ubuntu-latest
    steps:
      - uses: fumieval/tocenbough@v0
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          threshold: 10
```
