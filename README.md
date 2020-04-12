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

# Aliases

## git co \<branch|commit>
### Example Usage
`git co master`
### Description
Checks out a specific branch or commit. Short-hand for `git checkout <branch|commit>`.

## git currentbranch
### Example Usage
`git currentbranch`
### Description
Display the name of the currently checked out branch.

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
`git rib master`
### Description
Begins the process of interactive rebasing the current branch against the `branch_name` argument. Defaults to `master` if no `branch_name` argument is specified.

## show-diff [commit_hash]
### Example Usage
`git show-diff abc123`
### Description
Shows the changes introduced by the commit specified by the `commit_hash` argument. Defaults to `HEAD` if no `commit_hash` argument is specified.