# git-workflow

## Contributing
1. Branch off from main branch, `master` or `develop`, whichever the team decides. For this guide, let's use the `master` branch.
    * new feature - `feature/<feature-desc>`
    * bug fix - `bugfix/<issue #>-<fix-desc>`
    * hot fix - `hotfix/<version>`
    * release - `release/<version>`
2. Rebase often to keep code in-sync
  * if you are using phpstorm - you can simply use `cmd + t` and set to rebase and stash
![Alt text](/img/img1.png?raw=true "PHP Storm SYNC")
  * using terminal - simplify syncing by using the ff. script https://gist.github.com/miguelgonz/9fc4cb57c07c52e5f980
3. When ready, merge changes to `master` branch
4. Push `origin/master` including tags
5. Delete create branch

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