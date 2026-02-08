[GitFlow AVH cli tool](https://github.com/petervanderdoes/gitflow-avh)

    git checkout master
    git pull
    git describe --tags
    git checkout #your feature branch
    git flow release start <TAG+1>
    git flow release publish <TAG+1>  # pushes a release branch to origin

    git flow release finish -m "v<TAG+1>" -Fp <TAG+1>
    # should automatically merge to master and back to develop and then checks out develop

    # make sure changes and tags are pushed
    git status
    git describe --tags

---

← [prev](./All-Together-Now.md) | [next](./quiz.md) → | 🏠 [home](./README.md)
