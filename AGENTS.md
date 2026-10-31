# Repository guidance

This core fork belongs to [AzerothCore Playerbots Portable](https://github.com/Syntax555/mod-playerbots-portable/blob/main/README.md).
Before editing, read its [repository rules](https://github.com/Syntax555/mod-playerbots-portable/blob/main/AGENTS.md), the shared
skills those rules require, [README](https://github.com/Syntax555/mod-playerbots-portable/blob/main/README.md),
[contributing guide](https://github.com/Syntax555/mod-playerbots-portable/blob/main/CONTRIBUTING.md) and
[core integration guide](https://github.com/Syntax555/mod-playerbots-portable/blob/main/docs/module-versions.md#core).
Those rules also apply when working in this fork alone and take precedence over
imported upstream branch, build and contribution instructions.

Commit validated core changes on `master`; pin the commit in the assembly's
`versions.lock.json` and record fixture-covered behavior commits in `forkChanges`.
Keep original upstream history, licenses and file notices. Never rewrite a
commit pinned by the assembly. Validate changes against the assembly's pinned
modules and relevant production fixtures before committing. Read relevant
`.agents/docs/` guidance for native C++, SQL and AzerothCore APIs.
