http://www.youtube.com/watch?v=mYjZtU1-u9Y

===========
PART 1
===========

1. Install GIT client by logging-in into git-scm.com.
2. Install git bash client.
3. Click Start => Click Hostname (Check for the contents of this directory)
4. Open git-bash client and run ls. (This output would be same as the previous output)
5. Create a project home directory

6. Go to properties of git bash and set project home directory by setting "Startin" property.
7. Doing an ls again will print the contents of project home directory.
8. From git-bash, run the following.

git config --global user.name "krishh"

9. From git-bash, run the following.

git config --global user.email "strongfocus15@gmail.com"

10. Go the parent directory of project directory that you want to version control.

11. git init <projectName>

example: git init Dasgupta

12. cd Dasgupta
13. git status (will show the status of each file/dir with respect to GIT)

View private files will be shows as untracked and in red color in git bash.

14. git add . (will recursively add all the files and current directory to the VOB)

15. git rm --cached <file> to remove the file that got added in only in local VOB.

16. git commit -m "Checkin the first version"

17. We can modify a file without checking out.
18. git status will then show the modified files in red color.
19. git add <fileName> will only add that file to VOB.

20. SOMETHING NEW TO GIT.

Each time before a file is committed, "git add" must be run on that file for adding that file in staging area.

21. Then run "git commit -m "Comment me" " to commit the changes.
22. "git diff" will automatically identify the modified files and run diff.
 "git diff" will only show the difference between unstaged elements.
23. "git diff --cached" will show the the diffs between current and staged elements.

24. If the "git log" output is too long, enter "Shift + zz" to exit from the log.
25. git log --oneline will give the summary of the directory.

26. "git commit -a -m "Learning git"" will automatically added the new / modified files into staging area and then commit the changes.
27. "git status -s" will simply show the list of modified files.

28. Inorder to connect to GitHub and upload code to GitHub, ssh keys must be generated.
SSH keys use RSA asymmetric public/private keys.

28.1. SSH keys need to be generated manually whenever we use GitBash client.

ssh-keygen -t rsa -C "strongfocus15@gmail.com"

28.2. SSH keys will be automatically used whenever we use Windows Git client.

28.3. ssh -T git@github.com for verifying the connection.

29. Organizations must be used when using teams.

30. Upload to github using the following command.

a. git remote add origin git@github.com:rama777/Dasgupta.git
b. git push -u origin master (or)
git push github master (if you used github as name in step a)

===========
PART 2
===========

http://www.youtube.com/watch?v=8r_IErxmoUc

1. goto github.com
2. Create a github account.
3. Create a github repository.

4. Inorder to connect to GitHub and upload code to GitHub, ssh keys must be generated.
SSH keys use RSA asymmetric public/private keys.

4.1. SSH keys need to be generated manually whenever we use GitBash client.

ssh-keygen -t rsa -C "strongfocus15@gmail.com"

4.2. SSH keys will be automatically used whenever we use Windows Git client.

4.3. ssh -T git@github.com for verifying the connection.

5. Organizations must be used when using teams.

6. Upload to github using the following command.

a. git remote add origin git@github.com:rama777/Dasgupta.git
b. git push -u origin master (or)
git push github master (if you used github as name in step a)

7. Logon to git-scm.com and install Windows Git Client.
8. Login using GitHub user id / email. At this point GitHub global repositories can be seen but it does not show local repos.
9. Perform the following to show the local repos.

9.1. Go to Tools => Options and change default storage directory to local Git home directory. 
9.2. Click on Scan for Repos and add the directories.

10. Click on Create to create a new repos.
11. Create README.md to describe the nature of repos.

=========================
PART 3
=========================

1. git branch (will list all current branches. There will always be a master branch.)
2. git branch zoi_12345 (will create a new branch zoi_12345)
3. git branch (will list all current branches. There will now be master and zoi_12345 branches. Active branch will be shown as starred.)
4. git checkout zoi_12345 (will switch to zoi_12345 branch)


?????????????????????????????????????????????????????????????????????????????????????????????

1. How do we upload the newly created branch to remote GIT Server / GitHub?

?????????????????????????????????????????????????????????????????????????????????????????????


5. git remote add github git@github.com:rama777/DasGupta
6. git push github zoi_1 (This will upload zoi_1 branch to remote repository)
7. git pull github master (will update the master branch from remote master branch to local master branch)
8. git checkout zoi_1 (will switch the branch to zoi_1)
9. git merge master (will merge from master branch to zoi_1 branch)
10. Enter ZZ to exit out of git log.

######################################################################
Always PULL before doing PUSH
Git Bash conflicts resolving procedure is different from Git GUI client.
######################################################################

11. .gitignore file will contain the pattern of files that will be ignored by GIT.

======================
PART 4
======================

1. git commit -a -m "Comments"
2. git pull github master
3. git push github master

######################################################################
Always PULL before doing PUSH
Git Bash conflicts resolving procedure is different from Git GUI client.
######################################################################

4. For resolving merge conflicts using GUI client, do the following.

4.1. git add .
4.2. git rebase --continue
4.3. Open the file and resolve the conflicts manually and save
4.4. commit and publish in GUI client

5. For resolving merge conflicts in Git Bash client, do the following.

4.1. git add .
4.2. git push github master
4.3. Open the file and resolve the conflicts manually and save
4.4. git commit -a -m "Msg"

4.5. git push github master
4.6. git pull is a helper command that does following 2 commands automatically

a. git fetch (Downloads the code)
b. git merge (Merges from remote branch to local active branch without committed order)

4.7. git pull --rebase is a helper command that does following 2 commands automatically

a. git fetch (Downloads the code)
b. git rebase (Merges from remote branch to local active branch in committed order)

5. While a GitBash does git fetch followed by git merge, Git GUI does git fetch followed by git rebase.

Note: By default, git push does not transfer tags to remote repositories. You have to explicitly push tags to share them.

6. git tag -a ZMS_02.05.02.001 -m "First ADF release"
7. git push github ZMS_02.05.02.001 will push the specified tag
8. git push github --tag will push all tags to remote repository.

Generic Syntax: git push github <BranchName or TagName or --tag>

9. git checkout commit <HashCode> will checkout the specific version of a file.
10. git checkout master will reload the latest version of the all files.

11. git checkout ZMS_02.05.02.001 will set the config spec to retrieve from that tag.
12. git reset will uncheckout the changes. git reset will only uncheckout the changes that are committed to local staging area. It wont uncheckout the changes that are pushed to remote repo.
13. git revert will restore the file from before the most recent commit to remote repo. It wont remove history but will load the version that is before latest commit.

14. If a very old version need to be checkedout, git revert should be done sequentially.
15. There is a TortoiseGit available
 
http://code.google.com/p/tortoisegit
