# Final Project Submission – Introduction to Git and GitHub

**Repository (fork):** https://github.com/atharva80/mcino-Introduction-to-Git-and-GitHub
**Forked from:** https://github.com/ibm-developer-skills-network/mcino-Introduction-to-Git-and-GitHub

---

## Part 1 – GitHub UI (12 points)

### Task 1 – README.md (4 pts)
https://github.com/atharva80/mcino-Introduction-to-Git-and-GitHub/blob/main/README.md

### Task 2 – LICENSE, Apache 2.0 (2 pts)
https://github.com/atharva80/mcino-Introduction-to-Git-and-GitHub/blob/main/LICENSE

### Task 3 – CODE_OF_CONDUCT.md (2 pts)
https://github.com/atharva80/mcino-Introduction-to-Git-and-GitHub/blob/main/CODE_OF_CONDUCT.md

### Task 4 – CONTRIBUTING.md (2 pts)
https://github.com/atharva80/mcino-Introduction-to-Git-and-GitHub/blob/main/CONTRIBUTING.md

### Task 5 – simple-interest.sh (2 pts)
https://github.com/atharva80/mcino-Introduction-to-Git-and-GitHub/blob/main/simple-interest.sh

---

## Part 2 – Git CLI (8 points)

### Task 6 – forked-repo (2 pts)
```
$ curl -s https://api.github.com/repos/atharva80/mcino-Introduction-to-Git-and-GitHub | jq '{full_name, fork, html_url, parent: .parent.full_name, source: .source.full_name}'
{
  "full_name": "atharva80/mcino-Introduction-to-Git-and-GitHub",
  "fork": true,
  "html_url": "https://github.com/atharva80/mcino-Introduction-to-Git-and-GitHub",
  "parent": "ibm-developer-skills-network/mcino-Introduction-to-Git-and-GitHub",
  "source": "ibm-developer-skills-network/mcino-Introduction-to-Git-and-GitHub"
}
```

### Task 7 – merge_branches (2 pts)
```
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
$ git merge bug-fix-typo
Updating 7e8f63a..463881e
Fast-forward
 simple-interest.sh | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```

### Task 8 – bug-fix-revert (2 pts)
```
$ curl -s https://api.github.com/repos/atharva80/mcino-Introduction-to-Git-and-GitHub/pulls/1 | jq '{url: .html_url, state, title, head: {ref: .head.ref, repo: .head.repo.full_name, fork: .head.repo.fork}, base: {ref: .base.ref, repo: .base.repo.full_name}}'
{
  "url": "https://github.com/atharva80/mcino-Introduction-to-Git-and-GitHub/pull/1",
  "state": "open",
  "title": "Revert typo fix in simple-interest.sh",
  "head": {
    "ref": "bug-fix-revert",
    "repo": "atharva80/mcino-Introduction-to-Git-and-GitHub",
    "fork": true
  },
  "base": {
    "ref": "main",
    "repo": "atharva80/mcino-Introduction-to-Git-and-GitHub"
  }
}
```

### Task 9 – github-branches (2 pts)
```
$ git branch -a -vv
  bug-fix-revert                cf550af [origin/bug-fix-revert] Revert "Fix typo in simple-interest.sh"
  bug-fix-typo                  463881e [origin/bug-fix-typo] Fix typo in simple-interest.sh
* main                          463881e [origin/main] Fix typo in simple-interest.sh
  remotes/origin/HEAD           -> origin/main
  remotes/origin/bug-fix-revert cf550af Revert "Fix typo in simple-interest.sh"
  remotes/origin/bug-fix-typo   463881e Fix typo in simple-interest.sh
  remotes/origin/main           463881e Fix typo in simple-interest.sh
```
