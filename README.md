# Task Git_1 for hh-school

##### 01. create repo (repo A)
```
~/hh_git_1$ git clone https://github.com/yarkinsv/repoA.git repoA
```
##### 02. repo A: create 1st commit with some files (file A, file B)
```
~/hh_git_1/repoA$ nano A.txt
~/hh_git_1/repoA$ nano B.txt
~/hh_git_1/repoA$ git add .
~/hh_git_1/repoA$ git commit -m "Added files A.txt and B.txt (repo A 1st commit)"
```
##### 03. repo A: create branch branch1 from master
```
~/hh_git_1/repoA$ git branch branch1
```
##### 04. clone the current repo (repo B)
```
~/hh_git_1$ git clone repoA repoB
```
##### 05. repo B, branch1: create 2nd commit containing new file (file C)
```
~/hh_git_1/repoB$ git checkout branch1
~/hh_git_1/repoB$ nano C.txt
~/hh_git_1/repoB$ git add .
~/hh_git_1/repoB$ git commit -m "Added file C.txt (repo B 2nd commit)"
```
##### 06. repo B: push changes to repo A
```
~/hh_git_1/repoB$ git push origin branch1
```
##### 07. repo A, branch1: modify line#1 in file C and commit
```
~/hh_git_1/repoA$ git checkout branch1
~/hh_git_1/repoA$ nano C.txt
~/hh_git_1/repoA$ git commit -a -m "Modified file C.txt (in repo A)"
```
##### 08. repo B, branch1: modify line#1 in file C and commit
```
~/hh_git_1/repoB$ nano C.txt
~/hh_git_1/repoB$ git commit -a -m "Modified file C.txt (in repo B)"
```
##### 09. repo B, branch1: fetch changes from repo A
```
~/hh_git_1/repoB$ git fetch
```
##### 10. repo B, branch1: merge in repoA's branch1 (resolve conflict)
```
~/hh_git_1/repoB$ git pull
~/hh_git_1/repoB$ nano C.txt
~/hh_git_1/repoB$ git commit -a -m "Merge commit: resolved conflict on file C.txt in repo B"
```
##### 11. repo A: add repoB as new remote
```
~/hh_git_1/repoA$ git remote add repoB ../repoB
```
##### 12. repo A, branch1: merge in repoB's branch1
```
~/hh_git_1/repoA$ git pull repoB branch1
```
##### push repos to github
```
~/hh_git_1/repoA$ git push origin master
~/hh_git_1/repoA$ git push origin branch1
~/hh_git_1/repoB$ git remote add github https://github.com/yarkinsv/repoB.git
~/hh_git_1/repoB$ git push github master
~/hh_git_1/repoB$ git push github branch1
```
