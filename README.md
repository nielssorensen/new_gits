# new_gits
repo of folly, merge conflicts, detached HEADs, and how to get out of them

1) Get into a detached HEAD state.
git checkout some random commit hash

2) Committing in detached HEAD state and making a home (new branch for detached HEAD commits)
  ** assume you've performed example 1)
  touch file, add, commit, note hash of commit
  git checkout $NEW_BRANCH_NAME $COMMIT_HASH; you now have a home for this commit
  (you can now do more work on this branch and/or merge it into any other branch)

3) Merge conflict A, keep all changes from both branches
  ** assume many branches, all have blah.txt with 3 lines of text
  
  - in feature branch
  Step 1) add a new line with text to file
  
  - in master branch
  Step 2) add a blank line to file
  Step 3) add a new line with other text to file
  
merge master into feature branch
remove lines <<<<< HEAD, ======, >>>>> master
save, add, commit.  you now have all changes


4) Merge conflict B, keep only changes from master
  # Same as 2), same assumption, same steps

merge master into feature branch
remove all lines from <<<<< HEAD to ======, and >>>>> master
save, add, commit.  you now have only changes from master

TODO:
5) Merge conflict C, keep no changes from either branch
after doing the two above, this should be simple
