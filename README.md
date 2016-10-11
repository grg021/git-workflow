# git-workflow

## Contributing
1. Branch off from main branch, `master` or `develop`, whichever the team decides. For this guide, let's use the `master` branch.
    * new feature - `feature/<feature-desc>`
    * bug fix - `bugfix/<issue #>-<fix-desc>`
    * hot fix - `hotfix/<version>`
    * release - `release/<version>`
    
    ``` 
    git checkout -b feature/new-feature 
    ```
2. Rebase often to keep code in-sync
  
      ``` 
      git fetch
      git rebase origin/master
      ```
3. When ready, push branch to remote

    ``` 
    git push -u origin feature/new-feature 
    ```
4. Create a pull request (https://goo.gl/qXJ4s4)
5. Once merged to master, delete feature branch on local

Visual Diagram - https://guides.github.com/pdfs/githubflow-online.pdf

## Release
1. Branch off a point in master

    ```
    git checkout -b release/1.0.0
    ```
2. Once ready, tag top of branch to create new release and merge into `master`

    ```
    git tag 1.0.0
    git checkout master
    git merge release/1.0.0
    ```
3. Push to `origin/master` including the tag

    ```
    git push origin master --tags
    ```
4. Delete `release` branch

    ```
    git branch -d <branch_name>
    ```
5. Add release notes (you can also do this in the repo e.g. bitbucket)

## Hotfix
1. Branch off from release tag that you want to fix
    
    ```
    git checkout 1.0.0
    git checkout hotfix/2.0.1
    ```
2. Commit hot fix
3. Once ready, tag top of branch e.g. `2.0.1` to create new release and merge into master
4. Delete hotfix branch
5. add release notes (you can also do this in the repo e.g. bitbucket)

## Resolving Stale Pull Requests
A "stale" pull request is one that is no longer up to date with the main line of development e.g. master branch, and it needs to be updated before it can be merged into the project. 

The most common reason why pull requests go stale is due to conflicts: if two pull requests both modify similar lines in the same file, and one pull request gets merged, the unmerged pull request will now have a conflict. 

Sometimes, a pull request can go stale without conflicts: perhaps the branch was created when someone had accidentally merged failing unit tests to the master branch. Regardless of the reason, if your pull request has gone stale, you will need to rebase your branch onto the latest version of the master branch before it can be merged.

1. fetch latest changes in remote and sync local branch w/ remote

   ```
   git fetch origin
   git checkout feature/x
   git pull origin feature/x
   ```
2. start to rebase feature branch (make sure you are in feature branch)

   ```
   git rebase
   ```
3. During this time, you will likely see messages such as conflicts in files. If this happens you need to resolve those conflicts and continue to rebase.
   
   ```
   vi file # edit file w/ conflict to resolve
   git add . # add back file
   git rebase --continue # continue to rebase
   ```
Just a side note, if you are using phpstorm resolving conflicts can be done by right-clicking on the file, hover to "git" and select "resolve conflict"

4. Once done w/ rebasing, push back changes to remote

   ```
   git push origin feature/x --force
   ```
5. Proceed w/ the pull request as is

## Resources
* https://barro.github.io/2016/02/a-succesful-git-branching-model-considered-harmful/
* http://endoflineblog.com/gitflow-considered-harmful
* http://endoflineblog.com/follow-up-to-gitflow-considered-harmful
* https://www.atlassian.com/git/tutorials/comparing-workflows
