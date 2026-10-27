# Task: Incremental Codebase Cleanup

Your goal is to reduce tech debt by safely deleting unnecessary code, documentation, and duplication **without changing functionality**.

Run up to **10 small cleanup rounds** in a single session.

### Rules

1. **Find cleanup opportunities:** Unused imports, dead code, unused functions, duplicate helpers, obsolete feature flags, stale comments, and outdated or redundant documentation.

2. **Prioritize deletion over refactoring.** Prefer straightforward, provably safe removals. Don't introduce new abstractions or rewrite working code.

3. **Keep every round small:** Maximum 3–5 files and 300 lines removed per round. If you discover 10,000 lines worth deleting, split the work into many independent rounds. Never delete everything at once.

4. **Verify before deleting:** Search for references across the repository. Consider dynamic imports, external consumers, configuration, and tests. If something might still be used, leave it alone.

5. **Run checks after every round:** Relevant tests, linting, and type checking. Do not proceed with an unverified change. If a check fails because of your changes, revert or fix them.

6. **Self-review every round:** Inspect your own diff as a skeptical code reviewer. Look for accidental behavior changes, broken references, and unnecessary edits. If subagents are available, use an independent reviewer agent.

7. **Commit each successful round separately.** Each commit should contain exactly one logical cleanup and be independently revertible.

8. **Repeat:** After reviewing and committing one round, identify the next safest cleanup opportunity.

### Restrictions

- Do not change application behavior, public APIs, or business logic.
- Do not delete code based only on assumptions.
- Do not delete documentation that might still be useful.
- Do not combine unrelated cleanups.
- Do not make large sweeping changes.
- Do not skip verification to move faster.

### Final Report

After completing the rounds, report:

- Number of completed rounds and commits
- Files and lines removed
- Types of cleanup performed
- Tests/checks passed or unavailable
- Additional opportunities that require human review

**Success means a smaller, cleaner codebase with unchanged behavior—not the maximum possible number of deleted lines.**
