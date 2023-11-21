# Workflows for Project Automation

GitHub Project (beta) の自動化に関するワークフローを提供します。

## Notice
- このレポジトリは外部（dependabot）が参照するため、publicのままにしてください。（privateにするとエラーになります。）

## Usage

```yaml
name: Issue automation

on:
  issues:
    types:
      - opened

jobs:
  auto-set-project:
    uses: annai-inc/workflows-project-automation/.github/workflows/set-project.yml@main
    with:
      project-number: 10
      project-owner-org: ${{ github.repository_owner }}
      field-names: Priority,Iteration
      field-values: normal,Iteration 1
    secrets:
      github-token: ${{ secrets.PAT_PROJECT_AUTOMATION }}
```

see more details: [Definitions of workflow inputs](https://github.com/annai-inc/workflows-project-automation/blob/main/.github/workflows/set-project.yml#L5)
