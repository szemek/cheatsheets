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

#### Rebase with initial (root) commit

`git rebase -i --root master`

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

#### Rewrite your git history - change author in interactive rebase

```
git rebase -i master
```

Change `pick` to `edit`.

Repeat:

```
git commit --amend --author="Author Name <email@address.com>" --no-edit
git rebase --continue
```


#### Remove unnecessary files from git history

`git filter-branch -f --tree-filter 'rm -rf path/to/files' HEAD`

Add `--prune-empty` to remove empty commits.

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

#### Set pager to display whole diff

```
git config --global core.pager cat
```

#### Clear reflog

```
git reflog expire --expire=0 --all
```

#### Delete ref after filter-branch

```
git update-ref -d refs/original/refs/heads/master
```

#### Trace the evolution of the line range

```
git log -L <start>,<end>:<file>
```

#### Stop tracking a remote branch

```
git branch -d -r origin/<remote branch name>
```

#### Return git root directory

```
git rev-parse --show-toplevel
```

#### Display references refs/heads in a remote repository

```
git ls-remote --heads git@github.com:username/repository.git
```

#### Show diff like in GitHub's PR

```
git diff master...branch
```

#### Checkout content of specific commit

```
git checkout -f <sha> -- .
```

#### Diff two files outside any repository

```
git diff --no-index <file1> <file2>
```

Reference: https://stackoverflow.com/a/19930478

#### Use SSH instead of HTTPS

```
git config --global url.ssh://git@github.com/.insteadOf https://github.com/
```

#### Configure line endings

```
git config --global core.autocrlf input
git add --renormalize .
```

https://docs.github.com/en/get-started/getting-started-with-git/configuring-git-to-handle-line-endings

#### Use noreply email and don't sign commits

```
git config --global alias.anonymous '!bash /usr/local/bin/git-anonymous'
```

```
#!/bin/bash

git config gpg.program ""
git config commit.gpgsign false
git config user.email 373530+szemek@users.noreply.github.com
```

# Ignore changed line by using regular expression

In `.git/config`:
```
[filter "ignore_development_team"]
	clean = "sed 's/DEVELOPMENT_TEAM = .*;/DEVELOPMENT_TEAM = \"\";/'"
[filter "remove_code_sign_identity"]
	clean = "sed '/.*CODE_SIGN_IDENTITY.*/d'"
```

In `.git/info/attributes`:

```
*.pbxproj filter=ignore_development_team
*.pbxproj filter=remove_code_sign_identity
```

## Other useful stuff

  * git plugin from [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
  * [hub](https://github.com/github/hub)
  * [git-up](https://github.com/aanand/git-up)
  * [git_tracker](https://github.com/stevenharman/git_tracker)

#### CodeCommit SSH issues

```
Host git-codecommit.*.amazonaws.com
   User AAAAAAAAAAAAAAAAAAAA
   IdentityFile ~/.ssh/id_codecommit
   # Add these to let the SSH client accept RSA keys
   PubkeyAcceptedAlgorithms +ssh-rsa
   HostkeyAlgorithms +ssh-rsa
```

Reference: [CodeCommit SSH issues](https://www.stephengream.com/codecommit-ssh-issues)
