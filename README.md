##Product Tools
```
Directory Structure
------------------------------
├── GitTools
│   └── git_log_tools.sh //change your git log user.name user.email so that github 									   //platform can view your commit activity.
└── README.md

```
###Product Tools Dtail
```
├── GitTools
│   └── git_log_tools.sh
the tool can change your "git log" information. 
for example : your "git log" user.name user.email
```
######Certainlily, There is a emample you can get.
When i get "git log" for git commit history. i always do that 

```
➜  FamilyEducationApp git:(master) ✗  git log 
```
the command line will output 

```
commit 24b2b9cdacc9a7266648980201f6cbd02857de03
Merge: 982d959 60e85ba
Author: mgoofyy <mgoofyy@gmail.com>
Date:   Fri Jun 3 00:24:24 2016 +0800

    Merge branch 'master' of https://github.com/mgoofyy/FamilyEducationApp

commit 982d959c669c3ca7343e9ecef2eb5c0dc36a6ab2
Author: mgoofyy <mgoofyy@gmail.com>
Date:   Sat Dec 5 02:46:19 2015 +0800

    Readme.me change2

commit 60e85ba56a9401b077fab3bd2d9aa2345c3aaeee
Author: goofyy <1163191060@qq.com>
Date:   Sat Dec 5 02:46:19 2015 +0800

    Readme.me change2

commit a7932333ea5e257dcb104ac52a697972f5a3c2e0
Author: mgoofyy <mgoofyy@gmail.com>
Date:   Sat Dec 5 02:43:37 2015 +0800

    Delete README
....and so on
```
so you can see that,the author is goofyy OR mgoofyy ,Undoubtedly,goofyy is me,mgoofyy is me. but i config the git config use goofyy in other computer.so the error appear。

So .What should I do ?
Okay, Don't worry！
u can slove it  with the ```git_log_tools.sh```

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
And U with be successful.So cool. YEAH


