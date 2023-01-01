
* Init from git-hub fork and test branch
$ repo --trace init --worktree -v -u git@github.com:borting/mymanifest.git --repo-rev=fix-worktree-root-dir --no-repo-verify

* Init from local
$ repo --trace init --worktree -v --repo-url='/home/borting/repos/git-repo' --no-clone-bundle --repo-rev=fix-worktree-root-dir --no-repo-verify git@github.com:borting/mymanifest.gi
