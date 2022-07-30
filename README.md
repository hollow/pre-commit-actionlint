# pre-commit-actionlint

A [pre-commit](https://pre-commit.com) hook for
[actionlint](https://github.com/rhysd/actionlint) compiled from Go sources
on-demand.

The actionlint repository provides
[hooks](https://github.com/rhysd/actionlint/blob/main/.pre-commit-hooks.yaml) to
run from a system-wide actionlint installation or Docker image, both of which
are usually not desirable.

Simply using the upstream repository with a custom golang hook doesn't work
because pre-commit uses a hardcoded `go install ./...` on the repository but the
actionlint command needs to be compiled from a subdirectory.

## Usage

Add this to your `.pre-commit-config.yaml`:

```yaml
- repo: https://github.com/hollow/pre-commit-actionlint
  rev: "v1.6.15"
  hooks:
    - id: actionlint
```
