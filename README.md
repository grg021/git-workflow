# git-workflow

## Development
1. pull from main branch, master or develop, whichever the team decides
2. use rebase vs merge
  * if you are using phpstorm - you can simply use cmd + T and set to rebase and stash
![Alt text](/img/img1.png?raw=true "PHP Storm SYNC")
  * using terminal - simplify syncing by using the ff. script https://gist.github.com/miguelgonz/9fc4cb57c07c52e5f980
3. push to main branch

## Release
1. create new branch off at a point in master
2. once ready, tag top of branch e.g. 2.0.1 to create new release and merge into master
3. delete release branch

## Hotfix
1. branch out from release tag that you want to fix e.g. 2.0.0
2. commit hot fix
3. once ready, tag top of branch e.g. 2.0.1 to create new release and merge into master
4. delete hotfix branch

