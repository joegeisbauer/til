# Rename Git Branch

You can rename a git branch even after commits have been made to it using one simple command. Maybe the work you set out to do was not accomplished, or something else had to be performed prior to the work you wanted to complete. If you are in an organization that likes to keep their branches specific to one piece of work and have nice branch names that explain that work, then this feature can come in pretty handy before submitting a PR. Simply go to the branch you want to rename and use the following command:

```
git branch -m <new-branch-name>
```

You can then push the branch to the remote repository as you normally would. If you had previously push the former branch to the remote repository, then you will need to delete it. Then, you can create your PR.