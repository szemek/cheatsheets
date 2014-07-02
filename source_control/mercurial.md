### Mercurial: command equivalence table

| Git command     | Hg command               | Notes                 |
|:--------------- |:------------------------ |:--------------------- |
| `git pull`      | `hg fetch; hg pull -u`   | enable FetchExtension |
| `git fetch`     | `hg pull`                |                       |
| `git push`      | `hg push -r .`           |                       |
| `git status`    | `hg status`              |                       |
| `git add -A .`  | `hg add .; hg addremove` |                       |
| `git clean -fd` | `hg purge`               | enable PurgeExtension |

[Git concepts - Mercurial](http://mercurial.selenic.com/wiki/GitConcepts)
