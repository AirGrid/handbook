# Branching

At AirGrid we follow [git flow](https://nvie.com/posts/a-successful-git-branching-model/) as our branching strategy. The following guide will give you just enough information to be able to succesfully branch and push changes to our repos!

The are two key branches:
- `main`
- `develop`

We consider the `HEAD` of `main` to be production running state and the `HEAD` of `develop` to have the most recent changes. 

As developers we create the following types of supporting supporting branches:
- `feature`: this will add new functionality to the app, service or job.
- `chore`: this updates dependencies, documentation or cleans up dead code.
- `fix`: this fixes a bug.
- `release`: this branch is cut from develop as a release candidate.
- `hotfix`: this branch will be merged directly to main & develop without a release candidate.

## Feature

When starting work on a new feature, we would execute the following commands:

```bash
$ git checkout develop 
$ git pull origin develop
$ git checkout -b feature/my-new-feature-branch
```

This way we have the most recent changes from `develop`, and then we can cut our new feature branch. We can then begin the fun part and start throwing down code 😊. After hours of crafting and testing some high quality and readable code, we have [commited](commits.md) our changes into our local branch and are ready to open a pull request.

```bash
$ git add .
$ git commit -m 'feat: a clear and descriptive summary of the commit changes'
$ git push origin feature/my-new-feature-branch
```

We can open a PR through the Github UI, please see this [guide](pull-request.md) for how to make PR's great again.

## Branch Naming

Prefixing of branches should be done by branch type:

```bash
# this branch fixes a bug
$ git checkout -b fix/render-of-button-outside-table

# this branch adds a feature
$ git checkout -b feature/add-page-traffic-graph
```

Notice the verbosity of the branches, please avoid trying to create the shortest branch name possible, the following is not a good name:

```bash
$ git checkout -b fix/bug
```

## References

- [Git Flow Cheatsheet](https://danielkummer.github.io/git-flow-cheatsheet/)
