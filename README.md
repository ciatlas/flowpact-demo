# flowpact demo

A small repository that shows what [flowpact](https://github.com/ciatlas/flowpact) catches.

[Pull request #1](https://github.com/ciatlas/flowpact-demo/pull/1) adds a Windows leg to the test matrix but leaves
out its `config`. GitHub evaluates the missing matrix key to an empty string, the called workflow skips its tests on
Windows (`if: inputs.config != ''`), and the run stays green. flowpact reports it on the pull request.

- `.github/workflows/pipeline.yml` calls `tests.yml`, which calls `run-suite.yml` once per matrix entry.
- `.github/workflows/flowpact.yml` runs the [flowpact action](https://ciatlas.github.io/flowpact/docs/action) on every
  pull request.

The pull request stays open as a demo; it is not meant to be merged.
