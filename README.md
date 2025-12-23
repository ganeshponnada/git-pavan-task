user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ git init
Initialized empty Git repository in C:/Users/user/Desktop/Git pavan/.git/

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ mkdir folder-1 folder-2 folder-3

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ touch folder-1/file1.txt folder-1/file2.txt folder-1/file3.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ touch folder-2/file1.txt folder-2/file2.txt folder-2/file3.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ touch folder-3/file1.txt folder-3/file2.txt folder-3/file3.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ ls
folder-1/  folder-2/  folder-3/

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ ls folder-1
file1.txt  file2.txt  file3.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ git add .

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ git commit -m "Added folder-1, folder-2, folder-3 with empty files"
[master (root-commit) 047595a] Added folder-1, folder-2, folder-3 with empty files
 9 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 folder-1/file1.txt
 create mode 100644 folder-1/file2.txt
 create mode 100644 folder-1/file3.txt
 create mode 100644 folder-2/file1.txt
 create mode 100644 folder-2/file2.txt
 create mode 100644 folder-2/file3.txt
 create mode 100644 folder-3/file1.txt
 create mode 100644 folder-3/file2.txt
 create mode 100644 folder-3/file3.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ git log --oneline
047595a (HEAD -> master) Added folder-1, folder-2, folder-3 with empty files

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ git checkout -b first
Switched to a new branch 'first'

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ git branch
* first
  master

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ echo "change from first branch" >> folder-1/file1.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ echo "change from first branch" >> folder-1/file2.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ echo "change from first branch" >> folder-1/file3.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ echo "change from first branch" >> folder-2/file1.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ echo "change from first branch" >> folder-2/file2.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ echo "change from first branch" >> folder-2/file3.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ git add .
warning: in the working copy of 'folder-1/file1.txt', LF will be replaced by CRLF the next time Git touches it
warning: in the working copy of 'folder-1/file2.txt', LF will be replaced by CRLF the next time Git touches it
warning: in the working copy of 'folder-1/file3.txt', LF will be replaced by CRLF the next time Git touches it
warning: in the working copy of 'folder-2/file1.txt', LF will be replaced by CRLF the next time Git touches it
warning: in the working copy of 'folder-2/file2.txt', LF will be replaced by CRLF the next time Git touches it
warning: in the working copy of 'folder-2/file3.txt', LF will be replaced by CRLF the next time Git touches it

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ git commit -m "Modified folder-1 and folder-2 files in first branch"
[first b33dd9c] Modified folder-1 and folder-2 files in first branch
 6 files changed, 6 insertions(+)

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ git checkout master
Switched to branch 'master'

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ git checkout -b second
Switched to a new branch 'second'

user@GaneshGani MINGW64 ~/Desktop/Git pavan (second)
$ git branch
  first
  master
* second

user@GaneshGani MINGW64 ~/Desktop/Git pavan (second)
$ echo "change from second branch" >> folder-3/file1.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (second)
$ echo "change from second branch" >> folder-3/file2.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (second)
$ echo "change from second branch" >> folder-3/file3.txt

user@GaneshGani MINGW64 ~/Desktop/Git pavan (second)
$ git add .
warning: in the working copy of 'folder-3/file1.txt', LF will be replaced by CRLF the next time Git touches it
warning: in the working copy of 'folder-3/file2.txt', LF will be replaced by CRLF the next time Git touches it
warning: in the working copy of 'folder-3/file3.txt', LF will be replaced by CRLF the next time Git touches it

user@GaneshGani MINGW64 ~/Desktop/Git pavan (second)
$ git commit -m "Modified folder-3 files in second branch"
[second 2a4b194] Modified folder-3 files in second branch
 3 files changed, 3 insertions(+)

user@GaneshGani MINGW64 ~/Desktop/Git pavan (second)
$ git checkout first
Switched to branch 'first'

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ git branch
* first
  master
  second

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ git merge second
hint: Waiting for your editor to close the file... unix2dos: converting file C:/Users/user/Desktop/Git pavan/.git/MERGE_MSG to DOS format...
dos2unix: converting file C:/Users/user/Desktop/Git pavan/.git/MERGE_MSG to Unix format...
Merge made by the 'ort' strategy.
 folder-3/file1.txt | 1 +
 folder-3/file2.txt | 1 +
 folder-3/file3.txt | 1 +
 3 files changed, 3 insertions(+)

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ git log --oneline --graph --all
*   fc76212 (HEAD -> first) Merge branch 'second' into first
|\
| * 2a4b194 (second) Modified folder-3 files in second branch
* | b33dd9c Modified folder-1 and folder-2 files in first branch
|/
* 047595a (master) Added folder-1, folder-2, folder-3 with empty files

user@GaneshGani MINGW64 ~/Desktop/Git pavan (first)
$ git checkout master
Switched to branch 'master'

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ git merge first
Updating 047595a..fc76212
Fast-forward
 folder-1/file1.txt | 1 +
 folder-1/file2.txt | 1 +
 folder-1/file3.txt | 1 +
 folder-2/file1.txt | 1 +
 folder-2/file2.txt | 1 +
 folder-2/file3.txt | 1 +
 folder-3/file1.txt | 1 +
 folder-3/file2.txt | 1 +
 folder-3/file3.txt | 1 +
 9 files changed, 9 insertions(+)

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ git log --oneline --graph --all
*   fc76212 (HEAD -> master, first) Merge branch 'second' into first
|\
| * 2a4b194 (second) Modified folder-3 files in second branch
* | b33dd9c Modified folder-1 and folder-2 files in first branch
|/
* 047595a Added folder-1, folder-2, folder-3 with empty files

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ cat folder-1/file1.txt
change from first branch

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ cat folder-2/file3.txt
change from first branch

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ cat folder-3/file2.txt
change from second branch

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ cd ~/Desktop/"Git pavan"

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ git remote add origin https://github.com/ganeshponnada/git-pavan-task.git

user@GaneshGani MINGW64 ~/Desktop/Git pavan (master)
$ git branch -M main

user@GaneshGani MINGW64 ~/Desktop/Git pavan (main)
$ git push -u origin main
Enumerating objects: 14, done.
Counting objects: 100% (14/14), done.
Delta compression using up to 8 threads
Compressing objects: 100% (11/11), done.
Writing objects: 100% (14/14), 1.08 KiB | 158.00 KiB/s, done.
Total 14 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), done.
To https://github.com/ganeshponnada/git-pavan-task.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

user@GaneshGani MINGW64 ~/Desktop/Git pavan (main)
$ git push origin first
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: Create a pull request for 'first' on GitHub by visiting:
remote:      https://github.com/ganeshponnada/git-pavan-task/pull/new/first
remote:
To https://github.com/ganeshponnada/git-pavan-task.git
 * [new branch]      first -> first

user@GaneshGani MINGW64 ~/Desktop/Git pavan (main)
$ git push origin second
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: Create a pull request for 'second' on GitHub by visiting:
remote:      https://github.com/ganeshponnada/git-pavan-task/pull/new/second
remote:
To https://github.com/ganeshponnada/git-pavan-task.git
 * [new branch]      second -> second

user@GaneshGani MINGW64 ~/Desktop/Git pavan (main)
$
