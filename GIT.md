# Register on [Bitbucket](https://bitbucket.org) or [Github](https://github.com/) and create repository

# Initialize you repo
```bash
mkdir /path/to/your/project
cd /path/to/your/project
git init
git remote add origin https://snorch@bitbucket.org/your_login/project_name.git
```
# Configure GIT user
```bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```
# Make your first commit
```bash
cat README.md
# My first Project
git add README.md
git commit -m 'Initial commit: add README.md'
git push -u origin master
```
# View GIT repository
Clone git repository
```bash
git clone https://bitbucket.org/snorch/cs454.git
git clone https://github.com/xemul/criu.git
```
Show commit log

    git log
    commit 717d6a512aa8bc1501927a7ce9f4363bd41ae00e <- HEAD
    Author: Andrew Vagin <avagin@virtuozzo.com> <- author
    Date:   Tue Mar 15 09:23:00 2016 +0300 <- date

        cr-dump: getpriority() can return a negative value <- commit message subject

        Since getpriority() can legitimately return the value -1, it is necessary <- commit message
        to clear the external variable errno prior to the call, then check
        it afterward to determine if -1 is an error or a legitimate value.

        Cc: Filipe Brandenburger <filbranden@google.com>
        Fixes: 16e673c2f6a0 ("cr-check: Inspect errno on syscall failures")
        Signed-off-by: Andrew Vagin <avagin@virtuozzo.com>
        Acked-by: Cyrill Gorcunov <gorcunov@openvz.org>
        Signed-off-by: Pavel Emelyanov <xemul@virtuozzo.com>

    commit 9f5c378ff1c252277115102478abe1ece05414a8
    Author: Pavel Emelyanov <xemul@virtuozzo.com>
    Date:   Mon Mar 14 11:32:00 2016 +0300

        check: Call sbrk to get current brk

        According to man, glibc brk reports 0 on success, but we need current brk

        Signed-off-by: Pavel Emelyanov <xemul@virtuozzo.com>
        Acked-by: Cyrill Gorcunov <gorcunov@openvz.org>
        Cc: Saied Kazemi <saied@google.com>
    ...

Show commit changes, for HEAD and specific commit
```bash
git show
git show <commit_ID>
```
Go to specific commit/branch/tag
```bash
git checkout <commit_ID>
```
Show current changes, relative to HEAD
```bash
git diff
```
# Edit GIT repository
Did changes, - commit it
```bash
git add file_name.cpp <- changed file
git commit
-- Or --
git commit -a -m "subsystem: my first commit message"
```
Save patch to file
```bash
git format-patch HEAD -1 -s -o path/to/file/
```
