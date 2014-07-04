## Git

Some git commands gathered.

#### Set colors in git

`git config --global color.ui true`

#### Set editor for commits messages

`git config --global core.editor vim`

#### Simple push

`git config --global push.default simple`

#### Rebase when pulling from remote repository

`git config --global branch.autosetuprebase always`

#### Force existing branches to use rebase

`git config branch.branch.rebase true`

#### Merge without fast-forward (with merge commit)

`git merge branch --no-ff`

#### Amend commit & reset author

`git commit --amend --reset-author`

#### Add removed files

`git add -A .`

#### Interactively add hunks to stage phase

`git add -p`

#### Cherry-pick without making commit

`git cherry-pick commit -n`

#### Prune removed remote branches

`git fetch -p`

#### Clean untracked files and directories

`git clean -fd`

#### Set rebase by default

`git config --global branch.autosetuprebase always`

#### Push branch & set upstream reference

`git push -u origin branch`

#### Rewrite your git history with specific author & committer email

```
git filter-branch -f --env-filter '
    export GIT_AUTHOR_EMAIL=email@here.com
    export GIT_COMMITTER_EMAIL=email@here.com
' -- --all
```

#### Rewrite your git history - update details for specific committer

```
git filter-branch --commit-filter '
        if [ "$GIT_COMMITTER_NAME" = "<Old Name>" ];
        then
                GIT_COMMITTER_NAME="<New Name>";
                GIT_AUTHOR_NAME="<New Name>";
                GIT_COMMITTER_EMAIL="<New Email>";
                GIT_AUTHOR_EMAIL="<New Email>";
                git commit-tree "$@";
        else
                git commit-tree "$@";
        fi' HEAD
```


#### Remove unnecessary files from git history

`git filter-branch -f --tree-filter 'rm -rf path/to/files' HEAD`

#### Update local branch when remote was pushed with `--force`

```
git fetch --all
git checkout branch
git reset --hard remote/branch
```

#### Diff stat since yesterday

`git diff @{yesterday} --stat`

#### Globally ignore some files

Add to `~/.gitignore`

```
.DS\_Store
*.sw?
```
and run command `git config --global core.excludesfile ~/.gitignore`

#### Update branch without switching to it

```
git fetch origin branch:branch
```

#### Assume unchanged

```
git update-index --assume-unchanged filename
```

## Other useful stuff

  * git plugin from [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
  * [hub](https://github.com/github/hub)
