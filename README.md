# semantic-basic

Basic semantic-release environment

# Branching strategy

The most applicable branching strategy is [Trunk Based Development](https://trunkbaseddevelopment.com/).

Simple:

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

With [short-lived feature branches](https://trunkbaseddevelopment.com/short-lived-feature-branches/):

```mermaid
gitGraph
    commit
    commit
    branch release-1
    checkout release-1
    commit
    branch feature
    checkout feature
    commit
    commit
    checkout release-1
    merge feature
    branch fix
    checkout fix
    commit
    checkout release-1
    merge fix
    commit
    commit
    checkout main
    merge release-1
    commit
```

Notes:

- Use squash and merge strategy (all commits from child branch are squashed into single one) for feature and fix branches to merge into release branch
- Use rebase and merge strategy (all commits from release branch are moved to upstream branch) for release branches
