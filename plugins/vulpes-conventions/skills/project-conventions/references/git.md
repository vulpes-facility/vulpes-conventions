# Git

## Branch strategy

Select the strategy by the release model of the product.\
When the project does not name a strategy, use GitHub flow.

| Strategy | Use it when | Long-lived branches | Work branches | Merge | Production fix |
| --- | --- | --- | --- | --- | --- |
| GitHub flow | You deploy one version, often (web apps, services) | `main` | `<type>/<topic>` from `main` | Squash merge to `main` | Branch from `main`, merge, deploy |
| Trunk-based development | Many small merges each day, with feature flags | `main`, optional `release/<version>` | `<type>/<topic>` from `main`, for at most a few days | Squash merge to `main` | Fix on `main`, then cherry-pick to the release branch |
| Git flow | You support more than one released version at the same time | `main`, `develop` | `feature/<topic>`, `release/<version>`, `hotfix/<version>` | Merge commit (`--no-ff`) | `hotfix/<version>` from `main`, merge to `main` and `develop` |
| GitLab flow | Only when the project uses it already | `main`, one branch for each environment | `<type>/<topic>` from `main` | Squash merge to `main`, then merge `main` into each environment branch in order | Fix on `main` first, then merge it down |

1. Write the branch strategy of the project in `README.md`.
2. Use the branch names of the strategy.\
   When the strategy does not give names, name a branch `<type>/<topic>`.\
   Use a commit type from the table in "Commit messages", and a topic in lower-case kebab-case (for example, `feat/order-cancel`).
3. `main` MUST always build and pass the tests.
4. Protect each long-lived branch.\
   Require a pull request and passing CI checks.\
   Refuse force pushes and deletion.
5. Keep a work branch short.\
   Delete it after the merge.
6. With squash merge, set the default squash commit message of the repository to the pull request title.\
   Without this setting, GitHub uses the commit message when the pull request has only one commit.

## Commit messages

Write each commit message in the Conventional Commits 1.0.0 form:

```text
<type>(<scope>)!: <description>

<body>

<footers>
```

1. Use only the types in this table (`@commitlint/config-conventional`).

   | Type | Use it for |
   | --- | --- |
   | `feat` | A new feature for users |
   | `fix` | A bug fix for users |
   | `perf` | A change that makes the code faster |
   | `refactor` | A code change that does not add a feature and does not fix a bug |
   | `style` | A change to the format only, with no change to the behavior |
   | `test` | A change to tests only |
   | `docs` | A change to documentation only |
   | `build` | A change to the build system or to dependencies |
   | `ci` | A change to the CI configuration |
   | `chore` | Other maintenance that does not change the source code or the tests |
   | `revert` | A revert of an earlier commit |

2. Use the package name of the app or package that the commit changes as the scope (for example, `feat(api): add order cancel`).\
   When a commit changes many apps or packages, write no scope.
3. Write the description as a command (`add`, not `added` or `adds`).\
   Start it with a lower-case letter.\
   Do not put a period at the end.
4. Keep the header at 100 characters or less.\
   Keep each line of the body and of the footers at 100 characters or less.
5. In the body, tell why you make the change, when the description does not show it.
6. For a breaking change, put `!` after the type or the scope.\
   Also add a `BREAKING CHANGE:` footer that tells what the users must change.
7. Write each pull request title in the same form as a commit message.

- Check the messages with commitlint and `@commitlint/config-conventional`.\
  In a pnpm workspace, also extend `@commitlint/config-pnpm-scopes`.\
  It accepts the package names without the npm scope (`@acme/api` becomes `api`), and `global`.
- Run commitlint in a `commit-msg` hook with lefthook.
- Also run commitlint in CI, because `git commit --no-verify` skips the hooks.\
  With squash merge, CI checks the pull request title.\
  With merge commits, CI checks each commit in the pull request.

## Signed commits

1. When the host requires signed commits for the repository, sign each commit.\
   For example, a GitHub ruleset or branch protection rule with "Require signed commits", or a GitLab push rule "Reject unsigned commits".
2. Sign with a GPG, SSH, or S/MIME key, and add its public key to your account on the host.\
   Without the public key, the host cannot verify the signature, and it can refuse the push.

## Versions and tags

1. Give each released app and package a Semantic Versioning number.\
   `feat` changes the minor version.\
   `fix` changes the patch version.\
   A breaking change changes the major version.
2. Make the versions, the tags, and `CHANGELOG.md` with release-please.\
   Do not edit them by hand.
3. Keep `release-please-config.json` and `.release-please-manifest.json` at the root.\
   Run release-please in CI on the branch that you release from.
4. release-please opens a release pull request.\
   When you merge it, release-please makes the tag and the release.
5. Tag each release `<component>-v<version>`, the default of release-please (for example, `api-v1.4.0`).\
   When the repository releases only one version, set `include-component-in-tag` to `false`.\
   Then the tag is `v<version>`.
6. Do not move or delete a tag after you push it.
7. release-please works with GitHub.\
   When the repository is on a different host, use a release tool that supports that host, for example semantic-release.
