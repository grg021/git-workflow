# git-workflow

## Development
1. pull from main branch, `master` or `develop`, whichever the team decides. For this guide, let's use the `master` branch.
2. use rebase vs merge
  * if you are using phpstorm - you can simply use `cmd + t` and set to rebase and stash
![Alt text](/img/img1.png?raw=true "PHP Storm SYNC")
  * using terminal - simplify syncing by using the ff. script https://gist.github.com/miguelgonz/9fc4cb57c07c52e5f980
3. push to `master` branch

## Release
1. create new branch off at a point in master e.g. `release`
2. once ready, tag top of branch e.g. `1.0.0` to create new release and merge into `master`
3. push to `origin/master` including the tag
4. delete `release` branch

## Hotfix
1. branch out from release tag that you want to fix e.g. `hotfix/2.0.1`
2. commit hot fix
3. once ready, tag top of branch e.g. `2.0.1` to create new release and merge into master

4. delete hotfix branch

## Resources
* https://barro.github.io/2016/02/a-succesful-git-branching-model-considered-harmful/
* http://endoflineblog.com/gitflow-considered-harmful
* http://endoflineblog.com/follow-up-to-gitflow-considered-harmful