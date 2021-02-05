Git hooks are run to ensure the code quality of the codes being committed and pushed.

- On commit it will run: `goimports`, `golint`, `gosec`
- On Push it will run: `go vet`, `go test`

## Installation

```bash
cp -a hooks/. <YOUR-REPO-FOLDER>.git/hooks
```

## Skip Hooks

In some cases, you would want to skip running the hooks (e.g: config change, other file changes, etc.). Use the below environment variable:

```
SKIP_HOOKS=1
```

For example

```
SKIP_HOOKS=1 git push origin features/git-hooks
