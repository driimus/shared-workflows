# Shared Workflows

Set of reusable Github Actions workflows

## Usage

Check out the [official documentation](https://docs.github.com/en/actions/using-workflows/reusing-workflows#calling-a-reusable-workflow) on calling reusable workflows.

### Examples

#### `pr-lint-project`

Populate a project board with new PRs using `pr-link-project`:

```yml
on:
  pull_request:

jobs:
  link-project:
    uses: driimus/shared-workflows/.github/workflows/pr-link-project.yml@main
    with:
      project_name: "My automated broject board"
      column_name: "In progress"
```

#### `lint` and `test`

Single workflow for testing and linting a Node.js project:

```yml
on:
  push:

jobs:
  test:
    uses: driimus/shared-workflows/.github/workflows/test.yml@main
    with:
      node-version: 20
    # Optional Turborepo credentials to use for Remote Caching
    secrets:
      turbo_token: ${{ secrets.TURBO_TOKEN }}
      turbo_team: ${{ secrets.TURBO_TEAM }}

  lint:
    uses: driimus/shared-workflows/.github/workflows/lint.yml@main
    # Optional Turborepo credentials to use for Remote Caching
    secrets:
      turbo_token: ${{ secrets.TURBO_TOKEN }}
      turbo_team: ${{ secrets.TURBO_TEAM }}
```
