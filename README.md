# git_submodule_tutorial
## P1
* To add submodule:
git submodule add <url repository>


https://www.youtube.com/watch?v=ZYq3NJnO08U
* To pull all submodule run 2 command:
git submodule init
git submodule update

Luu y: 2 lenh nay chi co tac dung voi file .gitmodules o folder hien tai, cac submodule trong submodule se ko update


## P2
### clone mainproject with submodule_updaterd 21:03
https://www.youtube.com/watch?v=De8Bc1VxcGQ

git clone <url repo> --recursive
or
git clone <url repo> <inside new name folder> --recursive

ex: git clone https://github.com/devshop2019/git_submodule_tutorial.git --recursive
ex: git clone https://github.com/devshop2019/git_submodule_tutorial.git folder_1 --recursive
ex: git clone https://github.com/devshop2019/git_submodule_tutorial.git folder_1/folder1a/folder1a1 --recursive

Voi P2 cac submodule trong submodule se update tat ca

## P3
https://stackoverflow.com/questions/1030169/easy-way-to-pull-latest-of-all-git-submodules

If it's the first time you check-out a repo you need to use --init first:

git submodule update --init --recursive     // kxn test OK: Update toan bo submodule (ke ca submodule trong submodule) voi commit theo repo goc
For git 1.8.2 or above, the option --remote was added to support updating to latest tips of remote branches:

git submodule update --recursive --remote   // kxn test OK: Update toan bo submodule (ke ca submodule trong submodule) voi commit cuoi cung cua tung submodule
This has the added benefit of respecting any "non default" branches specified in the .gitmodules or .git/config files (if you happen to have any, default is origin/master, in which case some of the other answers here would work as well).

For git 1.7.3 or above you can use (but the below gotchas around what update does still apply):

git submodule update --recursive
or:

git pull --recurse-submodules
if you want to pull your submodules to latest commits instead of the current commit the repo points to.

See git-submodule(1) for details
https://mirrors.edge.kernel.org/pub/software/scm/git/docs/git-submodule.html
## END

1. Clone repo co chua submodule:<br>
```git clone https://github.com/devshop2019/git_submodule_tutorial.git --recursive```

2. Update tat ca cac submodule ve commit cuoi cung cua tung submodule<br>
```git submodule update --recursive --remote```
3. Update tat ca cac submodule ve commit cua repo <br>
```git submodule update --recursive```
4. Add submodule vao thu muc con cua repo folder1\foder2<br>
```
cd ./folder1/folder2
git submodule add <url repository>
```