## Git

#### Q1. How can you check your current git version?

- [x] git --version


#### Q2. What command lets you create a connection between a local and remote repository?

- [x] git remote add new
- [x] git remote add origin


The command is git remote add. The new added connection can be named origin or new. The only constraints, although it is not documented AFAIK, is that the connection name needs to be acceptable to git-check-ref-format, and it cannot be repeated.
If the LinkedIn assessment asks this and you can choose just one option, then leave feedback.

#### Q3. Describe what the following git commands do to the commit history.

```bash
git reset --hard HEAD~5
git merge --squash HEAD@{1}
```

- [x] Reset the commit branch back before the last 5 commits, then squashes them into a single commit

**Explanation:**

- `git reset --hard HEAD~5` resets the current branch to the commit just before the last 5 (see `man gitrevisions` for details about this notation and other cool alternatives like `HEAD@{2 days ago}`). As it is a hard reset, it will also overwrite every change in the working tree as well. See `man git-reset`.
- `git merge --squash HEAD@{1}` HEAD@{1} is where the branch was just before the previous command (again, see `man gitrevisions`). This command sets the state of the index to be as it would just after a merge from that commit. This whole operation could be a way to take 5 commits from a branch in which you started a new feature and squash them to a single commit, a meaningful one.

#### Q4. Your current project has several branches; master, beta, and push-notifications. You've just finished the notification feature in the push-notification branch, and you want to commit it to beta branch. How can you accomplish this?

- [x] Checkout the beta branch and run git merge push-notification

#### Q5. Which of the following is true you when you use the following command?

`git add -A`

- [x] All new and updated files are staged

#### Q6. What will the following command print to the Terminal?

`git remote -v`

- [x] A list of remote repositories and their URLs


#### Q7. Looking at the following commands, describe what is happening.

```bash
git checkout feature-user-location
git cherry-pick kj2342134sdf090093f0sdgasdf99sdfo992mmmf9921231
```

- [x] The commit is being cherry picked as the new HEAD of the commit history

**Explanation:** Commits aren't copied when cherry picking, they are cherry picked. The changes introduced by the commit are applied and a new commit is then created. This allow us to get specific changes as if they were patches (in the GIT's book, this is actually called [Patching](https://git-scm.com/book/en/v2/Appendix-C:-Git-Commands-Patching "See this in the GIT's book")). As a new commit is created upon feature-user-location, HEAD also changes to match it. You can see this in `cat .git/HEAD` and `cat .git/refs/heads/feature-user-location` for this case. See `man git-cherry-pick` for details.

**NOTE**: There are two versions of this question so far. The task is always "describe what is happening", the commands are always a `checkout` and a `cherry-pick`, and the correct answer is always the same.

#### Q8. What does the following command do to the git repository?

`git reset --soft HEAD^`


- [x] It sets HEAD to the previous commit and leaves changes from the undone commit in the stage/index.

#### Q9. You find a bug in your project, but can't locate where it was introduced in the commit history. How would you diagnose this problem?

- [x] Use git bisect to compare the buggy commit to an early commit that works as expected.

#### Q10. Why would the following command be used?

`git rebase -i HEAD~10`


- [x] To list the last 10 commits and modify them with either the squash or fixup command


#### Q11. Why would you use a pre-receive hook in your remote repository?

- [x] To execute a script when a remote receives a push that is triggered before any refs are updated


#### Q12. What option can you use to apply git configurations across your entire git environment?


- [x] `--global`


#### Q13. How could you squash multiple commits together without using git merge --squash?


- [x] Rebasing


#### Q14. If you cloned an existing git repository, what would happen?


- [x] A copy of the repository would be created on your local machine

#### Q15. How can you display a list of files added or modified in a specific commit?

- [x] Use the `diff-tree` command with the commit hash.


#### Q16. What files is this .gitignore programmed to leave out?

```shell
#.swift
build/

*.txt
*.metadata
```


- [x] All files in the build directory, as well as files ending with .txt or .metadata


A line starting with `#` serves as a comment. Hence `# .swift` does not do anything. See `man gitignore`.

#### Q17. After you make changes to a local repository, you run the following command. What will this do?

`git commit -a -m "Refactor code base"`


- [x] Adds all modified files to the staging area, then commits them with a message

#### Q18. After checking your git status you get the following output, which shows the file beta-notes.js in the commit but also unstaged. How can this situation occur?

```shell
Change to be committed:

(use "git reset HEAD <file>..." to unstage)
modified: beta-notes.js
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout --<file>..." to discard changes in working directory)

modified: beta-notes.js
```


- [x] beta-notes.js was staged, then modified afterwards, creating two different versions of the file


#### Q19. Where are files stored before they are committed to the local repository?


- [x] Staging area


#### Q20. What commands would you use to force an overwrite of your local files with the master branch?


- [x] ⠀

  ```bash
  git fetch --all
  git reset --hard origin/master
  ```

- The command `pull` is `fetch` followed by either `merge` or `rebase` (in this case, `merge`). We don't want to merge. Merge would be an action to our **repository**. We just want to overwrite our **local files**.

#### Q21. Which statement is true when you use the git add -A command?


- [x] All new and updated files from the working directory are staged to the index.


#### Q22. You find that your project has a tag and branch both named push-notifications, which causes confusion when trying to print out given reference. How can you specify which branch you want to look at?


- [x] use git show refs/head/push-notifications

[Reference](https://geedew.com/fixing-git-branch-and-tag-name-collision/)

#### Q23. Your team lead needs a list of all commits that will be moved before you perform a rebase. Which command can you use to access that information?


- [x] git rebase -i


#### Q24. What is the operation doing given the Git commands below?

```
git bisect start
git bisect bad 5d41402abc4b2a76b9719d911017c592
git bisect good 69faab6268350295550de7d587bc323d
```


- [x] It performs a binary search using a known bad commit and known good commit to determine which commit introduced a bug

#### Q25. In a situation where you have several commits for a single task, what is the most efficient way to restructure your commit history?


- [x] Squash the related commits together into a single coherent commit.


#### Q26. Which of the following is true of the git push command?

- [x] By default a push doesn't send tags to the remote repository.


[Reference](https://git-scm.com/book/en/v2/Git-Basics-Tagging#_sharing_tags)

#### Q27. After pushing commits to the remote repository for the first time using the command below, what shorthand command can you use in future?

```bash
git push -u origin master
```


- [x] git push

#### Q28. How would you create a custom shortcut or command across your git environment?


- [x] Create an alias usin the git config command.

#### Q29. What is the status of the beta-notes.js file in the following output?

```shell
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

modified: beta-notes.js
```


- [x] beta-notes.js is a tracked file and has been modified, but has not been added to the current commit.


#### Q30. What command would let you modify your previous commit?


- [x] --amend

#### Q31. What is the best way to characterize the git commit structure?


- [x] Data log


#### Q32. What change will the following command make to the staging area files?

`git rm --cached testfile.js`

- [x] testfile.js will be removed from the staging area and its changes no longer tracked.


#### Q33. After you've successfully merged two branches and committed the changes, what is the next step in keeping your git structure organized?


- [x] Run git rebase to move the current commit to its original location.

#### Q34. While modifying a file, you're unexpectedly assigned an urgent bug fix on another branch. How can you temporarily save your local work without committing?


- [x] Use git stash to save your work and come back later and reapply the stashed commit.

#### Q35. What command would you use to create a new git repository?


- [x] git init

#### Q36. While working on a feature branch you try to use "git rerere" to solve a recurring merge conflict but nothing is happening. What could be causing this issue?


- [x] "rerere.enabled" isn't enable in the config file.


#### Q37. Which setting determines what pager is used when Git pages output?


- [x] core.pager

#### Q38. What does commit object contain?


- [x] An SHA1 name, a 40-character string that uniquely identifies the commit object.

#### Q39. Which option enables inclusion of committer name in custom log format?


- [x] %cn

#### Q40. How many ways are present in Git to integrate changes from one branch into another?


- [x] 2


- **Explanation:** `In Git, there are two main ways to integrate changes from one branch into another: the merge and the rebase.`
- [Reference link](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)

#### Q41. Which user should be created first during setting up of SSH?

- [x] git


#### Q42. Which command will list tags with the 1.4.2 series?


- [x] git tag -I 'v1.4.2.\*'


#### Q43. Which of the following is an integration manager?


- [x] benevolent dictator


#### Q44. Which Git command begins tracking of a new file?

- [x] add

#### Q45. Which of the following is called dumb protocol?


- [x] HTTP

#### Q46. Which key press returns a set of suggestions to pick from, when writing a Git command?


- [x] Tab


#### Q47. Which of these terms best describes Git?

- [x] Distributed Version Control System


#### Q48. Which command gets a copy of an existing Git repository?


- [x] clone

#### Q49. How does Git think of its data?


- [x] Snapshot


#### Q50. Which option enables inclusion of author name in custom log format?


- [x] %an

#### Q51. Which version onwards did Git offer reversing a file back to what it looked like when last committed?


- [x] 1.6


#### Q52. Which strategy is used by Git for merging two branches?


- [x] recursive


#### Q53. What does refs store?

- [x] SHA-1 value


#### Q54. What Language is used in GIT?

- [x] C


#### Q55. What is usually the extension of file which has the public key?


- [x] pub

#### Q56. What is the difference between initializing a normal repo and a bare repo?


- [x] Bare repos do not come with working or checked-out source files.

#### Q57. How many individual commits can a single repository have?

- [x] any number of commits


#### Q58. What types of tags does Git support?


- [x] lightweight and annotated

#### Q59. After staging a series of changes to the index, which command could you use to review them prior to a commit?

- [x] git diff --cached


#### Q60. What does the git stash drop command do?

- [x] removes the most recent stash entry


#### Q61. What command creates a new branch from the currently checked-out branch?


- [x] `git checkout -b <nameOfBranch>`

#### Q62. After mistakenly staging a file named myFile to the index, how would you remove it from the index to exclude it from your next commit?


- [x] Use git reset myFile.txt.


#### Q63. What happens if you run this command from your master branch?

```bash
git checkout -b beta-test
```


- [x] A new branch called beta-test will be created and switched to.


#### Q64. How does Git internally manage branches?

- [x] by creating a pointer to the most recent snapshot/commit for the branch.


#### Q65. You want to perform a git reset but cannot recall all of the available options. What command would you use to see a description of them?

- [x] git help reset


#### Q66. What is a remote repository?


- [x] a version of the repository hosted on the internet or network that is pushed to or pulled from by collaborators

#### Q67. After modifying some existing files in a repository, you decide to discard the changes. What command can you use?


- [x] git checkout

#### Q68. After starting to merge a feature branch into your master branch, you encounter a merge conflict and decide you do not want to perform the merge. How can you stop the merge and restore to the pre-merge state?


- [x] Use git merge --abort.


#### Q69. If you have several commits for a single feature, what is the most efficient way to restructure your commit history?


- [x] Use git squash to consolidate the commits together into a single coherent commit.


#### Q70. Which command correctly creates a lightweight tag?

- [x] `git tag v3.8.1`


#### Q71. What is the main issue with using git rebase when working with multiple developers?


- [x] Rebase deletes all commit history for the new feature branch.

#### Q72. What Git workflow is used by teams that collaborate on a single branch and avoid creating long-lived development branches?


- [x] Trunk-Based Development


#### Q73. Which option on the git log command allows you to limit output to commits made after certain data?

- [x] `--since`


#### Q74. How would you delete unreachable objects older than a specified time from your project database?


- [x] `git prune --expire <time>`

#### Q75. What conflicts can occur when forcing a push after rebasing?

- [x] The remote master branch could have existing changes overwritten.

#### Q76. How does this command alter the currently checked-out branch?

`git reset --soft HEAD^`


- [x] It sets HEAD to previous commit and leaves changes from the undone commit in the stage/index.


#### Q77. What is the difference between Git and SVN?


- [x] SVN is a centralized system, while Git is a distributed system.


#### Q78. This command is an example of what kind of tag?

`git tag -a v1.4 -m "ABCD v1.5"`


- [x] annotated


#### Q79. What is the difference between a soft reset (`git reset --soft`) and a hard reset (`git reset –hard`) ?

- [x] A soft reset only changes the commit that HEAD points to, while a hard reset resets the index and working tree to match the specified commit, discarding any changes.


#### Q80. Consider the following Git workflow:

![image](images/Git-WorkFlow.png)
Which of the following options is correct ?


- [x] `1. Master 2. Hotfix 3. Develop 4. Feature 5. Release`

#### Q81. What information does the git config file store?


- [x] local and global repository options


[Reference](https://www.atlassian.com/git/tutorials/setting-up-a-repository/git-config#:~:text=The%20git%20config%20command%20is,modify%20a%20configuration%20text%20file.)

#### Q82. What is version control?


- [x] a system that shows, tracks, and controls changes to a set of files over time


#### Q83. What is the difference between using the git stash and git stash pop commands?


- [x] git stash creates a stash entry, while git stash pop places the saved state onto the working directory.

#### Q84. Which command can be used to list the branches that have been merged into the currently checked-out branch?


- [x] git branch --merged


#### Q85. How would you configure Git to abort a commit if a smoke test script fails?


- [x] Create a pre-commit hook to trigger the script.


#### Q86. Which use case is NOT a good candidate for a Git hook?

- [x] state dependent environment changes


#### Q87. After starting to work on a new feature and creating new files in the working directory related to it, the customer determined the feature was no longer required. What command can be used to remove the untracked files from the working directory ?

- [x] `git clean -f`


#### Q88. What information do Git reflogs (reference logs) store?


- [x] updates to branch tips and other references in the local repository


#### Q89. You have just completed rebasing your master branch and need to manually update the remote master, even though there is a merge conflict. How can you accomplish this?


- [x] `git push --force-with-lease`

#### Q90. What is the difference between `git fetch` amd `git pull`


- [x] `git fetch` updates remote tracking branches with changes from a remote repository, while `git pull` updates remote tracking branches with changes from a remote repository and merges them into their corresponding local branches.


#### Q91. What command displays the difference between the working tree and the stage/index area, as well as files not tracked by Git?


- [x] `git status`


#### Q92. Your current repository has three branches: master, beta, and push-notifications. You have just finished the notification feature and commit the changes to the push-notification branch, and you want to include them in the beta branch. How can you accomplish this?

- [x] Check out the beta branch and run git merge push-notifications.


#### Q93. You would like to restore some previously stashed work to a new branch. How can you do that?


- [x] Run git stash branch <branch name>.

[reference here](https://stackoverflow.com/questions/6925099/git-stash-changes-apply-to-new-branch)

#### Q94. What is the difference between git branch -d and git branch -D?


- [x] -d deletes the local branch, while -D deletes the local branch regardless of push and merge status.


#### Q95. You stashed three sets of changes but cannot remember the contents of the first stash entry. What command would you use to see the details of the changes in the first of the three stash entries?

- [x] git stash show -p stash@{2}


[reference here](https://stackoverflow.com/questions/10725729/see-whats-in-a-stash-without-applying-it)

#### Q96. Which statement is true of the git push command?

- [x] By default, a push doesn't send tags to the remote repository.


[reference here](https://git-scm.com/book/en/v2/Git-Basics-Tagging)
