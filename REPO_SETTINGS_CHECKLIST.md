# Repository Settings Checklist

Use this baseline for every repository in `mvs5465-test`.

## Branch protection and merge controls

- Require pull requests before merging to `main`
- Require status checks:
  - `review / review`
  - `commitlint / commitlint`
- Require branches to be up to date before merging (`strict: true`)
- Allow only squash merges
- Allow auto-merge
- Automatically delete head branches on merge (`delete_branch_on_merge: true`)
- Always suggest updating pull request branches (`allow_update_branch: true`)
- Restrict PR creation to collaborators only (`pull_request_creation_policy: collaborators_only`)

## Workflow standardization

- `.github/workflows/claude-pr-review.yml` exists in each repo and calls:
  - `mvs5465-test/.github/.github/workflows/claude-pr-review.yml@main`
- `.github/workflows/commitlint.yml` exists in each repo and calls:
  - `mvs5465-test/.github/.github/workflows/commitlint.yml@main`
- Callers are configured so required checks appear as:
  - `review / review`
  - `commitlint / commitlint`

## Security and quality defaults

- Secret scanning enabled
- Default branch set to `main`
