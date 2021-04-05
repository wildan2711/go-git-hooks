Git hooks are run to ensure the code quality of the codes being committed and pushed.

- On commit it will run on staged files: `goimports`, `golint`, `gosec`, `gitleaks`
- On Push it will run on all files: `go vet`, `go test`

## Installation

```bash
git clone https://github.com/wildan2711/go-git-hooks.git

cp -a go-git-hooks/hooks/. <YOUR-REPO-FOLDER>/.git/hooks
chmod +x <YOUR-REPO-FOLDER>/.git/hooks/*
```

## Skip Hooks

In some cases, you would want to skip running the hooks (e.g: urgent hotfixes, minor config change, etc.). Use the below environment variable when running git commit or push:

```
SKIP_HOOKS=1
```

For example

```
SKIP_HOOKS=1 git push origin features/git-hooks
