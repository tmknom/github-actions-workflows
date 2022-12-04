# github-actions-workflows

A collection of Reusable Workflows for GitHub Actions

## Description

This repository provides the following Reusable Workflows:

- [Lint Workflow](/.github/workflows/lint.yml)
- [Docs Workflow](/.github/workflows/docs.yml)
- [Release Workflow](/.github/workflows/release.yml)

## Lint Workflow

### Usage

```yaml
jobs:
  lint:
    uses: tmknom/github-actions-workflows/.github/workflows/lint.yml@v0
```

### Inputs

N/A

### Permissions

N/A

## Docs Workflow

### Usage

```yaml
jobs:
  docs:
    uses: tmknom/github-actions-workflows/.github/workflows/docs.yml@v0
    with:
      yaml-file: action.yml
      markdown-file: README.md
      ref: ${{ github.event.pull_request.head.ref }}
```

### Inputs

| Name | Description | Type | Default | Required |
| :--- | :---------- | :--- | :------ | :------: |
| ref | The git ref | `string` | n/a | yes |
| markdown-file | The Markdown file for the injection target | `string` | `README.md` | no |
| yaml-file | The YAML file for the action or the reusable workflow | `string` | `action.yml` | no |

### Permissions

| Scope | Access |
| :--- | :---- |
| contents | write |

## Release Workflow

```yaml
jobs:
  release:
    uses: tmknom/github-actions-workflows/.github/workflows/release.yml@v0
    with:
      level: ${{ inputs.level }}
```

### Inputs

| Name | Description                           | Type | Default | Required |
| :--- |:--------------------------------------| :--- | :------ | :------: |
| level | bump to [`major` / `minor` / `patch`] | `string` | `minor` | no |

### Permissions

| Scope | Access |
| :--- | :---- |
| contents | write |
| pull-requests | write |

## Changelog

See [CHANGELOG.md](/CHANGELOG.md).

## License

Apache 2 Licensed. See [LICENSE](/LICENSE) for full details.
