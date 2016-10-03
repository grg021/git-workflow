# git-workflow

## Contributing
1. Branch off from main branch, `master` or `develop`, whichever the team decides. For this guide, let's use the `master` branch.
    * new feature - `feature/<feature-desc>`
    * bug fix - `bugfix/<issue #>-<fix-desc>`
    * hot fix - `hotfix/<version>`
    * release - `release/<version>`
    
    ``` git checkout -b feature/new-feature ```
2. Rebase often to keep code in-sync
  * using terminal
  
      ``` 
      git fetch
      git rebase origin/master
      ```
  * to simplify syncing try using the ff. script https://gist.github.com/miguelgonz/9fc4cb57c07c52e5f980
3. When ready, rebase and push branch to remote

    ``` 
    git fetch
    git rebase origin/master
    git push -u origin feature/new-feature 
    ```
4. Create a pull request
5. Once merged to master, delete feature branch on local

## Release
1. Branch off a point in master e.g. checkout specific commit #
2. Once ready, tag top of branch e.g. `1.0.0` to create new release and merge into `master`
3. Push to `origin/master` including the tag
4. Delete `release` branch
5. Add release notes (you can also do this in the repo e.g. bitbucket)

## Hotfix
1. Branch off from release tag that you want to fix e.g. `hotfix/2.0.1`
2. Commit hot fix
3. Once ready, tag top of branch e.g. `2.0.1` to create new release and merge into master
4. Delete hotfix branch
5. add release notes (you can also do this in the repo e.g. bitbucket)

## Resources
* https://barro.github.io/2016/02/a-succesful-git-branching-model-considered-harmful/
* http://endoflineblog.com/gitflow-considered-harmful
* http://endoflineblog.com/follow-up-to-gitflow-considered-harmful
* https://www.atlassian.com/git/tutorials/comparing-workflows