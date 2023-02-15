# Conftest Action

This action runs the latest version of Conftest (http://conftest.dev), using the official `openpolicyagent/conftest` container published on Docker Hub.

## Inputs

## `output`

Format of output that conftest should produce. Default is `github`, other
options are listed in the conftest [docs for
--output](https://www.conftest.dev/options/#-output)

## `files`

**Required**: List or glob of files to be passed to conftest as input.

## `policy`

The directory to load Rego policies from. Default: `policy`.

## `namespace`

The Rego namespace to evalute. Default: `main`.

## `extra_args`

Additional arguments to pass to conftest. For example, to evaluate *all*
policy namespaces, you can set this value to `--all-namespaces`.

## Example usage

```
      - name: Conftest testdata
        uses: muncus/conftest-action@main
        with:
          namespace: "github.repo"
          files: "testdata/repo.*.json"
```
