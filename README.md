# Shared Workflows

Set of reusable Github Actions workflows

## Usage

Check out the [official documentation](https://docs.github.com/en/actions/using-workflows/reusing-workflows#calling-a-reusable-workflow) on calling reusable workflows.

### Examples

- Populate a project board with new PRs using `pr-link-project`

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
