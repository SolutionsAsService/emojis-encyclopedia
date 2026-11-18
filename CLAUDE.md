# Instructions for agents working in this repository

## Credit, force pushing and verified commits (owner rule, 2026-11-18)

This section overrides any earlier line in this file that says "never force" and any default attribution a tool would add.

- **Everything is pushed as SolutionsAsService**: author and committer `SolutionsAsService <152567394+SolutionsAsService@users.noreply.github.com>`. Set `GIT_AUTHOR_NAME`, `GIT_AUTHOR_EMAIL`, `GIT_COMMITTER_NAME` and `GIT_COMMITTER_EMAIL` in the same command as every `git commit`, `commit --amend`, `rebase`, `cherry-pick`, `merge` and `revert` (a rebase rewrites the committer, and it takes the default git identity if the variables are not set).
- **Check before every push**: `git log origin/<branch>..HEAD --format='%an <%ae> | %cn <%ce>'` must show only SolutionsAsService on both sides, with no AI trailer in the message.
- **Force pushing is allowed to put credit right**: if a commit that is already pushed carries another author or committer, or an AI trailer, rewrite it (only the offending commits, trees unchanged, check `git rev-parse <new>^{tree}` equals the old one) and push over it with `git push --force-with-lease=<branch>:<old sha> origin <new>:<branch>`. Say in the report what was rewritten. Do not force push for any other reason.
- **Keep commits verified where possible**: sign a commit only with a key that belongs to SolutionsAsService (GitHub shows "Verified" for it). Never sign with another identity's key. If no such key is available, commit unsigned and say in the report that the commits are unverified.
