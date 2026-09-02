# Git Notes

A summary of the Git concepts and commands I have covered while building my DevOps foundations.

## GIT BASICS

Git is a version control system used to track changes to files and code.

It allows me to see what has changed, keep a history of my work and safely work on different versions of a project.

Some core commands I have used include:

```bash
git init
git status
git add
git commit
git log
```

## STAGING AND COMMITS

Git uses a staging area before changes are committed.

`git add` - Adds changes to the staging area.

`git commit` - Saves a snapshot of the staged changes.

`git status` - Shows the current state of the working directory and staging area.

This helped me understand that changing a file, staging it and committing it are separate stages.

## BRANCHES

Branches allow changes to be developed separately from the main version of a project.

```bash
git branch
git switch <branch>
git switch -c <branch>
```

I used branches to work on features independently before combining them back into `main`.

## MERGING

Merging combines changes from different branches.

```bash
git merge <branch>
```

I practised creating feature branches, making commits and then merging the completed work back into the main branch.

I also learned how merge conflicts can happen when Git cannot automatically decide how different changes should be combined.

## REMOTE REPOSITORIES

GitHub allowed me to store my Git repositories remotely and use them as part of my DevOps portfolio.

Important commands included:

```bash
git remote -v
git push
git pull
git clone
```

`git push` sends local commits to a remote repository, while `git pull` brings remote changes into the local repository.

## UNDOING AND RECOVERING CHANGES

I practised several ways of handling mistakes and recovering previous work.

These included:

```bash
git reset
git revert
git reflog
```

`reset` can move the current branch back to another commit.

`revert` creates a new commit that reverses an earlier change.

`reflog` records movements of `HEAD` and helped me understand how apparently lost work can sometimes be recovered.

## STASHING AND CHERRY-PICKING

I also worked with:

```bash
git stash
git cherry-pick
```

`git stash` temporarily stores uncommitted changes so I can work on something else without committing unfinished work.

`git cherry-pick` applies a specific commit from another branch onto the current branch.

## GITIGNORE

`.gitignore` tells Git which files or patterns should not be tracked.

This is particularly important for files that do not belong in a repository, such as environment files, generated files or sensitive information.

## PRACTICAL GIT WORK

During my Git exercises, I practised:

- Creating and managing repositories
- Staging and committing changes
- Creating feature branches
- Merging branches into `main`
- Working with local and remote repositories
- Pushing and pulling changes
- Using `.gitignore`
- Stashing unfinished work
- Resetting and reverting changes
- Recovering work with `reflog`
- Applying individual commits with `cherry-pick`
- Working through Git-based command-line challenges

## KEY TAKEAWAYS

Git has helped me understand how changes to a project can be tracked, organised and recovered rather than simply saving different copies of files.

The biggest thing I have taken from Git is understanding the workflow behind the commands. Knowing where my changes are, whether they are staged or committed, which branch I am working on and how that branch relates to the remote repository makes Git much easier to use.
