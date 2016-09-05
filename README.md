# How2Git

A small toy repo for a git workshop. 

# Ading a feature

Make sure you're on master
`git checkout origin master`

Create a new branch for the new feature. Use lowercase and underscore for spaces
`git checkout -b feature_a`

Make some changes, and stage them
`git add -A` 

`git commit -m "feat: add cool feature a`

If you've only made changes to existing files, adding and commiting can be done with a single command
`git commit -am "feat: add cool feature b`

# Commit

Commit your changes using a commit message on the following format

* `conf` - commit contains only configuration updates
* `feat` - commit adds new functionlity
* `fix`  - commit fixes a bug
* `ref`  - commit contains a refactor of existing code, no new functionality

Also, use imperative form in commit messgeas. That is, write what you intended to do, not what you did: "add new feature", not "added new feature"

NB: If you feel like your commit fits several of these tags, that probably means you're commiting too much at once. A single commit should only cover a single feature! If you did some refactoring, *and* updated some configurations, then create two separate commits: One for each. Also, if you feel like your commit message requires the word *and*, that probably is a sign that you're commiting too much!


# Workflow and Merging

Perhaps the most scary part of using git is the fear of losing work and resolving merge conflicts. However, these issues can mostly be avoided by using a swift workflow.

Example of workflow:

Add feature
```
git branch -b feature_c
echo some changes >> feature_c.txt
git add -A
git commit -am "feat: add neat feature c
```

Update your local master, and merge it into your new feature branch
```
git checkout master
git pull origin master
git checkout feature_b
git merge master
```

Make sure everything still works, and then merge your feature branch into the master

```
git checkout master
git merge feature_b
git push origin master
```

# Q & A
* What is origin?
Origin is the remote repository. On the other hand, HEAD is the current state of local repo on *your own* computer. 
