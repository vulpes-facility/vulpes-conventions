# Pull requests

1. Make each change on a branch, and merge it with a pull request.\
   The repository allows only squash merge, and uses the pull request title as the commit message.
2. Write each commit message and each pull request title as a Conventional Commit, by [`git.md`](../../plugins/vulpes-conventions/skills/project-conventions/references/git.md).\
   Write no scope, because the repository has one plugin.
3. Sign each commit.\
   The organization refuses unsigned commits on every branch.
4. Before you open a pull request, make a Task issue for the change.
5. Write the pull request description in the form of the organization template, `.github/pull_request_template.md` in [`vulpes-facility/.github`](https://github.com/vulpes-facility/.github).\
   The `REVIEW.md` of that repository tells how a reviewer checks the description.\
   Close the Task issue from the Related section (`- Closes #N`).
6. In each pull request that changes the plugin, change `version` in `plugin.json`, so that `claude plugin update` installs the change.\
   `feat` changes the minor version, `fix` changes the patch version, and a breaking change changes the major version.
