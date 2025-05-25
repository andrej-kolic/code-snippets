## Delete local branches without remote

update your local repository's knowledge of the remote branches and remove any remote-tracking branches that no longer exist on the remote:
```bash
git fetch --prune
```

list branches and watch for 'gone':
```bash
git branch -vv
```

delete local branches:
```bash
git branch -vv | grep ': gone]' | awk '{print $1}' | xargs -r git branch -d
```


## Delete local branches that have been merged

ensure you are on the main branch.

list the branches that would be deleted:
```bash
git branch --merged | grep -vE "(^\*|main|master)"
```

delete the merged local branches (safely):
```bash
git branch --merged | grep -vE "(^\*|main|master)" | xargs -n 1 git branch -d
```