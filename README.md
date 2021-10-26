# internet engineering HW1
This repo created for Third question of internet engineering assignement.
### task 1:
```
touch FileA.txt
git add FileA.txt
git commit -m "initial commit."
echo "This is not empty anymore." > FileA.txt
git commit --amend --no-edit
git push origin master
```
I use --no-edit flag because there was no need to change commit message.
### task 2:
```
echo "Some secrets..." > .env
git add .env
git commit -m "adding secrects"
git push origin master
git rebase --interactive HEAD~1
# in editor drop the secret commit
git push origin +master
```
in last command I use +master instead of master that is actually force push and will need not protected branch. 
### task 3:
```
echo "New file B" > FileB.txt
echo "New file C" > FileC.txt
git checkout -b file-b-c
git add FileB.txt FileC.txt
git commit -m "new uncertain changes."
git push origin file-b-c
```
So my colleague can do their review on the code and merge it later.
```
git checkout file-b-c
# doing some review
git merge master
# merging this changes with new changes on master
git push origin master
```
### task 4:
```
#creating a branch named new-branch and adding 3 commits.
git checkout -b merge-2
git rebase --interactive --onto master  HEAD~3
# drop commit 1 and 3 and pick commit 2 in editor
git checkout master
git merge merge-2
git push origin master
# now the commit two merged two master
git checkout new-branch
git rebase --interactive --onto master  HEAD~3
# drop commit 2 and squash commit 3 and name squash commit "commit 1 and 3"
git checkout master
git merge new-branch
git push origin master
```

