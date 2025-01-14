# GitHub Actions and Workflows for maintaining dbt

A set of GitHub [Actions](https://docs.github.com/en/actions/creating-actions/about-custom-actions) and [Reusable Workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows) for automating common tasks related to developing, maintaining, and releasing dbt-core, database adapter plugins, and other dbt-labs open source projects. 

Actions and workflows should be self documented.  See individual actions for more info and instructions on how to use.

### Actions

- [Parse Semver Action](parse-semver)
- [Python Package Info Action](py-package-info)

### Workflows

- [Jira Issue Transition](.github/workflows/jira-transition.yml)
- [Jira Label Mirroring](.github/workflows/jira-label.yml)
- [Jira Issue Creation](.github/workflows/jira-creation.yml)
- [Changelog Existence Check](.github/workflows/changelog-existence.yml)
- [Core Triage Label Handling](.github/workflows/replace-label.yml)
- [Version bump and Changelog Generation](.github/workflows/version-bump.yml)

## Releasing

Either:

- Add a label to a PR (`bump:major`, `bump:minor`, `bump:patch`) to determine what part of the version to bump when merging PR. When the PR is merged, the [release GHA](https://github.com/dbt-labs/internal-actions/actions/workflows/release.yml) will create or update tags for the major and minor version (e.g. `v1`, `v1.1`).
- Create a new tag with the format `v#.#.#`. The [release GHA](https://github.com/dbt-labs/internal-actions/actions/workflows/release.yml) will create or update tags for the major and minor version (e.g. `v1`, `v1.1`).

## Development

- Each Action will have instructions for development.
- It is recommended to use [act](https://github.com/nektos/act) for testing locally where possible.
- Actions have a cooresponding workflow for automated testing.
- Here is [documentation](https://docs.github.com/en/actions/creating-actions) for creating custom actions.

## Debugging

You can enable debug logging for GHA be setting secret values for your repository. See [docs](https://docs.github.com/en/github-ae@latest/actions/monitoring-and-troubleshooting-workflows/enabling-debug-logging) for more info.

- Set `ACTIONS_RUNNER_DEBUG` to `true` to enable runner diagnostic logging.
- Set `ACTIONS_STEP_DEBUG` to `true` to enable run step debug logging.
