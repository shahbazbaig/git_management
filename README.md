# git_management
Different operations to perform for git repositories management

# Git repository creation
...
# Git clone
git clone <repo_name>

# Update online repository
git add -A 
OR 
git add <filename>
OR
git add *.extension

Then add commit using command 
git commit -m "message"

# Revert local commits
check git logs to select the header you want to keep

git reset --hard <commit header where you want to go>
NOTE: This will also remove the files from local directory

# Recover the accidently removed files during git reset --hard
git fsck --lost-found

this will returned back to lastest commit 
now use 
git rebase <commit header of the commit you want to keep>

OR 

git reset --hard <commit header you want to keep>

There are cases where rebase is not powerful enough. For example when you expect to face a lot of conflicts. In this case merge is a better solution:

git merge <commit header>

If instead you had a few commits one after another but you just want to pick the last one, rebase and merge won’t do. They would bring the whole branch back in master. That’s a situation for cherry-pick.

git cherry-pick <git header>

Once you know how to recover from bad mistakes, you’ll find that Git is not only a very powerful tool, but also a very forgiving one. As opposed to a motocross.

The following commands will help you figure you way out of most bad situations:

git show
git fsck −−lost-found
git diff
And these ones will actually get out of these bad situations:

git rebase
git cherry-pick
git merge
git apply

Reference:
[1] http://www.programblings.com/2008/06/07/the-illustrated-guide-to-recovering-lost-commits-with-git/


