### To install: brew install git-flow

### Commonly used command in git flow
1. git flow init
2. git flow [feature / release / hotfix] [start / finish / publish / pull] [ name ]

### Ideal sequence of commands
1. git flow init
2. git flow feature start some-feature
3. git flow feature finish some-feature
4. git flow feature publish some-feature
5. git flow feature pull some-feature
6. git flow feature track some-feature
7. git flow release start some-release [ BASE sha ]
8. git flow release publish some-release
9. git flow release track some-release
10. git flow release finish some-release
11. git push origin --tags
12. git flow hotfix start some-hotfix
13. git flow hotfix finish some-hotfix
14. git push origin main
15. git push origin develop


