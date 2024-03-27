
## Command line interface

User Guide - [Command Line Interface](https://www.mkdocs.org/user-guide/cli/#mkdocs-build)

### get-deps

Show required PyPI packages inferred from plugins in mkdocs.yml

Usage: `mkdocs get-deps [OPTIONS]`

```Shell
pifan@rpi4b-ubuntu~/Sites/mkdocs $ python3 -m mkdocs get-deps
markdown-checklist
mkdocs
mkdocs-material
pymdown-extensions
```

### build

Build the MkDocs documentation

Usage: `mkdocs build [OPTIONS]`

Name | Type | Description | Default
-----|------|-------------|--------
`-f`, --config-file | filename | Provide a specific MkDocs config. This can be a file name, or '-' to read from stdin. | None
`-d`, --site-dir | path | The directory to output the result of the documentation build. | None

### gh-deploy

Deploy your documentation to GitHub Pages

Usage: `mkdocs gh-deploy [OPTIONS]`

Name | Type | Description | Default
-----|------|-------------|--------
`-m`, --message | text | A commit message to use when committing to the GitHub Pages remote branch. Commit {sha} and MkDocs {version} are available as expansions | None
`-b`, --remote-branch | text | The remote branch to commit to for GitHub Pages. This overrides the value specified in config | None
`-r`, --remote-name | text | The remote name to commit to for GitHub Pages. This overrides the value specified in config
`--no-history` | boolean | Replace the whole Git history with one new commit. | False
`-d`, --site-dir | path | The directory to output the result of the documentation build. | None

## Deploying your docs

User Guide - [Command Line Interface](https://www.mkdocs.org/user-guide/cli/#mkdocs-build)

