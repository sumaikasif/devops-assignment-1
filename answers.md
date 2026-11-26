# DevOps Assignment 1

**Name:** Sumaika 
**Student ID:** 65651

## Part 3, Task 1

Commands:
```
mkdir -p ~/devops-assignment-1
cd ~/devops-assignment-1
git init
git config user.name "Sumaika"
git config user.email "sumaikasif@gmail.com"
```

Output:
Initialized empty Git repository in /home/sumaika/devops-assignment-1/.git/
Sumaika
sumaikasif@gmail.com

Explanation:
I created a new folder for the assignment and initialized a Git repository inside it.
Then, I set my name and email address so that my name will appear on all future commits I make.

## Part 3, Task 2

Commands:
```
touch README.md .gitignore
printf '*.log\ntmp/\n.env\n' > .gitignore
touch server.log
mkdir tmp
touch tmp/test.txt
touch .env
git status
git add .
git commit -m "Part 3 Task 2: Initial setup with README and gitignore"
```

Output:
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        README.md
        answer.md
        answers.md

nothing added to commit but untracked files present (use "git add" to track)

Explanation:
I created the required files and added rules to the .gitignore file.
The .gitignore file successfully prevented server.log, the tmp folder, 
and the .env file from showing up in git status.Finally, I staged
and committed the remaining files.

## Part 3, Task 3

Commands:
```
echo "This is my DevOps Assignment repository." >> README.md
git status
git add README.md
git status
git commit -m "Part 3 Task 3: Update README with description"
```

Output:
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   answers.md

no changes added to commit (use "git add" and/or "git commit -a")
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   answers.md

main XXXXXXX Part 3 Task 3: Update README with description
1 file changed, 1 insertion(+)

Explanation:
After editing README.md, the changes were in the **Working Directory**.
When I ran `git add`, the changes moved to the **Staging Area**.Finally, 
after running `git commit`, the changes were saved permanently in the **Repository**.


# Part 3, Task 4

Commands:

```
git branch -M main
git remote add origin git@github.com:sumaikasif/devops-assignment-1.git
git push -u origin main
git remote -v
git log --oneline
git push
```

Output:
origin  git@github.com:sumaikasif/devops-assignment-1.git (fetch)
origin  git@github.com:sumaikasif/devops-assignment-1.git (push)
87dfe02 (HEAD -> main, origin/main) Part 3: Final commit to complete Git setup
4385dfa Part 3 Task 4: Add notes file for 4th commit
c7539aa Part 3 Task 3: Update README with description
cb0cc1a Part 3 Task 2: Initial setup with README and gitignore

Explanation:
I created an empty repository on GitHub and connected it to my local repository using the SSH URL. 
I pushed my main branch to GitHub and verified the remote and commit history. I made sure there 
are at least four commits in the history by adding a final commit.

## Part 2, Task 1

Commands:
```
mkdir -p ~/assignment/linux/data/reports
mkdir -p ~/assignment/linux/data/archive
ls -R ~/assignment/linux
```

Output:
/home/sumaika/assignment/linux:
data

/home/sumaika/assignment/linux/data:
archive  reports

/home/sumaika/assignment/linux/data/archive:

/home/sumaika/assignment/linux/data/reports:

Explanation:
I used the `mkdir -p` command to create the nested directory structure. 
The `-p` flag creates parent directories if they do not exist. Then, I
 used the `ls -R` command to verify the structure recursively.

## Part 2, Task 2

Commands:
```
cd ~/assignment/linux
touch report.txt run.sh
chmod 640 report.txt
chmod 754 run.sh
ls -l
```

Output:
total 4
drwxr-xr-x 4 sumaika sumaika 4096 Nov 26 22:19 data
-rw-r----- 1 sumaika sumaika    0 Nov 26 22:20 report.txt
-rwxr-xr-- 1 sumaika sumaika    0 Nov 26 22:20 run.sh

Explanation:
I created two files, report.txt and run.sh. I used the numeric form of chmod to set their permissions. 
For report.txt, I used 640: The owner (6) has read and write, the group (4) has read only, and others (0) have no permissions.
For run.sh, I used 754: The owner (7) has read, write, and execute, the group (5) has read and execute, and others (4) have read only.

## Part 2, Task 3

Commands:
```
printf 'INFO start\nERROR disk full\nINFO user login\nWARN slow response\nERROR timeout\nINFO user logout\nERROR disk full\nINFO backup done\nWARN memory high\nERROR timeout\nINFO restart\nERROR disk full\n' > server.log
grep "ERROR" server.log | wc -l
grep "WARN" server.log | wc -l
grep "ERROR" server.log | grep "disk"
```


Output:
5
2
ERROR disk full
ERROR disk full
ERROR disk full

Explanation:
 The first command creates a sample log file.
 The second command uses `grep` to find "ERROR" lines and pipes them to `wc -l` to count them, which gives 5.
 The third command does the same for "WARN" lines, giving 2.
 The fourth command uses two `grep` commands piped together to show only the lines that contain both "ERROR" and "disk".
