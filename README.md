# Description
This is a collection of aliases that I like to use to optimize my git usage a little. I mostly use command line Git, so this makes my life a lot easier.


# Setup
I recommend that you do not copy these directly into the .gitconfig for your repository. While you certainly could, I instead recommend cloning this repository somewhere and adding it to the git repo(s) you want to use the aliases in.

To add it to a specific repo, run this command from within that repo.
```powershell
git config include.path "path\to\gitconfig"
```

To add it to all repos, run this command anywhere on the command line.
```powershell
git config --global include.path "path\to\gitconfig"
```

# Updates
In order to update your list of aliases, simply run `git pull` inside of this repo on your local machine. All of your git repos that utilize these aliases will now be able to use the new ones.

# Aliases

## git co \<branch|commit>
### Example Usage
`git co main`
### Description
Checks out a specific branch or commit. Short-hand for `git checkout <branch|commit>`.

## git current-branch
### Example Usage
`git current-branch`
### Description
Display the name of the currently checked out branch.

## git comp [pull_arguments]
### Example Usage
`git comp --rebase`
### Description
Checks out the main branch and executes a pull. If any `pull_arguments` are specified, these will be proxied to the `git pull` command. If main is not a valid branch, it falls back to using master (legacy standard).

## git graph
### Example Usage
`git graph`
### Description
Displays the history of the repo in a prettyfied format.

## git f
### Example Usage
`git f`
### Description
Short-hand for `git fetch`

## git feature [work_item]
### Example Usage
`git feature JIRA-1234`
### Description
Creates and checks out a new feature branch with the name `feature/work_item`. Defaults to `tmp` if no `work_item` argument is specified.

## git rib [branch_name]
### Example Usage
`git rib main`
### Description
Begins the process of interactive rebasing the current branch against the `branch_name` argument. Defaults to `main` if no `branch_name` argument is specified.

## show-diff [commit_hash]
### Example Usage
`git show-diff abc123`
### Description
Shows the changes introduced by the commit specified by the `commit_hash` argument. Defaults to `HEAD` if no `commit_hash` argument is specified.

## spp [pull_arguments]
### Example Usage
`git spp --rebase`
### Description
Stashes local changes, pulls, then pops stash to re-apply the stashed changes. The `git pull` command can be passed arguments using the `pull_arguments` specified after `git spp`

## find-withered-branches
### Example Usage
`git find-withered-branches`
### Description
Prints the remote branches with the 10 oldest heads. Can be used to find old, "withered" branches that should be deleted from the remote.


## ahead-behind [branch]
### Example Usage
`git ahead-behind origin/main`
### Description
Shows commits 'ahead' and 'behind' of the current branch and the provided remote branch. Defaults to origin/main if not provided, and automatically infers the current branch.

## soft-clean 
### Example Usage
`git soft-clean` 
### Description
Attempts to clean a project without removing commonly locally changed files. Currently excludes web.config, appsettings.json, app-config.json, and app.config

## delete-branches

### Example Usage
`git delete-branches [pattern]`

### Description

Deletes all local branches that match the pattern.  Pattern follows all `grep` rules.

## l

### example usage
`git l`

### Description
Runs `git log --oneline --graph`

## Compare-branch

### Example Usage
`git compare-branch origin/main`

### Description

List all commits on this branch but not on the target branch (Defaults to your default branch)
## s

### example usage
`git s`

### Description
Runs a simplified (compact) status command. Output looks like this:
```
## master...origin/master [behind 1]
 M README.md
 M gitconfig
```

## publish


### example usage
`git publish`

### Description
This alias is to publish a new branch to a remote the first time. Takes as a parameter, the remote to push to.  It will try to push a branch that matches the current branch's name to the given remote (defaulting to "origin").
