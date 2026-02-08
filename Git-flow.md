# Branching Strategies

GitFlow is one of several branching models. Consider what fits your team:

| Strategy | Best for |
|:---------|:---------|
| [GitFlow](https://nvie.com/posts/a-successful-git-branching-model/) | Scheduled releases, multiple versions in production |
| [GitHub Flow](https://docs.github.com/en/get-started/using-github/github-flow) | Continuous deployment, single production branch |
| [Trunk-Based Development](https://trunkbaseddevelopment.com/) | Small frequent merges, feature flags |

## GitFlow Example

[GitFlow AVH cli tool](https://github.com/petervanderdoes/gitflow-avh)

    git checkout main
    git pull
    git describe --tags
    git checkout #your feature branch
    git flow release start <TAG+1>
    git flow release publish <TAG+1>  # pushes a release branch to origin

    git flow release finish -m "v<TAG+1>" -Fp <TAG+1>
    # should automatically merge to main and back to develop and then checks out develop

    # make sure changes and tags are pushed
    git status
    git describe --tags

---

← [prev](./All-Together-Now.md) | [next](./quiz.md) → | 🏠 [home](./README.md)
