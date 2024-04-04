# semantic-basic

Basic semantic-release environment

# Branching strategy

Branching strategy is [Trunk Based Development](https://trunkbaseddevelopment.com/):

```mermaid
gitGraph
    commit
    commit
    branch fix-1
    checkout fix-1
    commit
    checkout main
    merge fix-1
    branch feature-1
    checkout feature-1
    commit
    commit
    commit
    checkout main
    merge feature-1
    commit
```

Notes:

- Use squash and merge strategy (all commits from child branch are squashed into single one) for feature and fix branches to merge into upstream (or trunk, or main)
