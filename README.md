## Course of action [check snapshots for corresponding state visuallization]
1. git flow init
2. First commit in develop:
    1. touch develop-1.txt
    2. ga .
    3. gc -m “add develop-1.txt”
3. git flow feature start feature-1
    1. Summary of actions:
        1. A new branch 'feature/feature-1' was created, based on 'develop'
        2. You are now on branch 'feature/feature-1'
4. First commit in feature-1:
    1. touch feature-1.1.txt
    2. ga .
    3. gc -m “add feature-1.1.txt”
5. git flow feature finish feature-1
    1. Summary of actions:
        1. The feature branch 'feature/feature-1' was merged into 'develop'
        2. Feature branch 'feature/feature-1' has been removed
        3. You are now on branch 'develop'
6. git flow feature start feature2
    1. Summary of actions:
        1. A new branch 'feature/feature2' was created, based on 'develop'
        2. You are now on branch 'feature/feature2'
7. Second commit in develop
    1. git checkout develop
    2. touch develop-2.txt
    3. ga .
    4. gc -m “add develop-2.txt”
8. git checkout feature/feature2
9. First commit in feature-2
    1. touch feature-2.1.txt
    2. ga .
    3. gc -m “add feature-2.1.txt”
10. Second commit in feature-2
    1. touch feature-2.2.txt
    2. ga .
    3. gc -m “add feature-2.2.txt”
11. git flow feature finish feature2
    1. Summary of actions:
        1. The feature branch 'feature/feature2' was merged into 'develop'
        2. Feature branch 'feature/feature2' has been removed
        3. You are now on branch 'develop'
12. git log --oneline
    1. feature2 changes are applied on top of ongoing develop branch changes
13. git flow release start 1.0.0
    1. Summary of actions:
        1. A new branch 'release/1.0.0' was created, based on 'develop'
        2. You are now on branch 'release/1.0.0'
    2. Follow-up actions:
        1. Bump the version number now!
        2. Start committing last-minute fixes in preparing your release
        3. When done, run: git flow release finish '1.0.0'
14. git checkout develop
    1. created a file release.sh
    2. ga .
    3. gc -m “add release.sh”
15. git checkout release/1.0.0
16. git merge develop release/1.0.0
17. Create first version bump: ./release.sh
18. git tag list: v1.0.0
19. First commit in release/1.0.0
    1. touch release-1.1.txt
    2. ga .
    3. gc -m “add release-1.1.txt”
20. Third commit in develop
    1. git checkout develop
    2. touch develop-3.txt
    3. ga .
    4. gc -m “add develop-3.txt”
21. Fourth commit in develop
    1. touch develop-4.txt
    2. ga .
    3. gc -m “add develop-4.txt”
22. git checkout release/1.0.0
23. git flow release finish 1.0.0
    1. Summary of actions:
    2. Latest objects have been fetched from 'origin'
    3. Release branch has been merged into 'main'
    4. The release was tagged 'v1.0.0'
    5. Release branch has been back-merged into 'develop'
    6. Release branch 'release/1.0.0' has been deleted
24. Fifth commit in develop
    1. git checkout develop
    2. touch develop-5.txt
    3. ga .
    4. gc -m “add develop-5.txt”
25. Sixth commit in develop
    1. touch develop-6.txt
    2. ga .
    3. gc -m “add develop-6.txt”
26. git checkout main
27. git flow hotfix start 1.0.1
    1. Summary of actions:
        1. A new branch 'hotfix/1.0.1' was created, based on 'main'
        2. You are now on branch 'hotfix/1.0.1'
    2. Follow-up actions:
        1. Bump the version number now!
        2. Start committing your hot fixes
        3. When done, run: git flow hotfix finish '1.0.1' 
28. Create second version bum: ./release.sh v1.0.1
29. git tag list: v1.0.0, v1.0.1
30. First commit in hotfix/1.0.0
    1. touch hotfix-1.1.txt
    2. ga .
    3. gc -m “add hotfix-1.1.txt”
31. Second commit in hotfix/1.0.0
    1. touch hotfix-1.2.txt
    2. ga .
    3. gc -m “add hotfix-1.2.txt”
32. git flow hotfix finish 1.0.1
    1. Summary of actions:
        1. Latest objects have been fetched from 'origin'
        2. Hotfix branch has been merged into 'main'
        3. The hotfix was tagged 'v1.0.1'
        4. Hotfix branch has been back-merged into 'develop'
        5. Hotfix branch 'hotfix/1.0.1' has been deleted
33. git log --online
    1. Hotfix commits were applied on top of develop fifth and sixth commit