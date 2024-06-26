 ## Hard vs. soft git resets

The key difference between git reset hard and soft commands is that a soft git reset does not revert staged or working tree files back to a previous state, while the hard git reset does.
Neither the git reset hard nor soft commands impact untracked files.

Git reset hard versus soft example
For this example, let’s envision a local Git repo with five commits. Each commit added a single new file:

The fifth commit added e.txt.
The fourth commit added d.txt.
The third commit added c.txt.
The second commit added b.txt.
The first commit added a.txt.
Here’s what a directory listing would look like:

/c/git reset hard vs soft (master)
$ ls
a.txt  b.txt  c.txt  d.txt  e.txt
The local Git commit history would be as follows:

/c/git reset hard vs soft (master)
$ git reflog
2e1dd0a HEAD@{0}: commit: Commit #5 - 5 files
868ca7e HEAD@{1}: commit: Commit #4 - 4 files
ebbbca3 HEAD@{2}: commit: Commit #3 - 3 files
882bf98 HEAD@{3}: commit: Commit #2 - 2 files
2f24f15 HEAD@{4}: commit: Commit #1 - 1 files
Git reset hard and soft commands
Let’s imagine the developer wants to git reset back to commit #3 (id ebbbca3). The developer can choose either of the two git reset syntaxes:

git reset --hard ebbbca3
git reset --soft ebbca3
git reset hard
If the developer performs a git reset hard, this removes files d.txt and e.txt from the filesystem, and the staging index is cleared if anything exists in it.

/c/git reset hard vs soft (master)
$ git reset --hard ebbbca3
$ ls
a.txt b.txt c.txt
The files d.txt and e.txt are gone from the filesystem. The git reset hard command reverts the working tree back to the previous commit’s state.

git reset soft
Compare the git reset hard to a soft git reset issued on the same Git history:

/c/git reset hard vs soft (master)
$ git reset --soft ebbbca3
$ ls
a.txt b.txt c.txt d.txt e.txt
As you can see, the hard git reset changes the filesystem. The soft git reset did not.

Not demonstrated in this example is that a hard git reset clears the index while the soft reset does not.

Both the hard and soft git reset commands provide the developer with a way to manipulate their local commit history. The key difference is how these two commands impact the Git index and working 

## Git Stash

git stash temporarily shelves (or stashes) changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on. Stashing is handy if you need to quickly switch context and work on something else, but you're mid-way through a code change and aren't quite ready to commit.

Stashing your work
The git stash command takes your uncommitted changes (both staged and unstaged), saves them away for later use, and then reverts them from your working copy. For example:

$ git status
On branch main
Changes to be committed:

## Umask & Chmod:

It too is used to define permissions for files and folders. The difference between umask and chmod is that umask changes the default permissions and thus the permissions for all newly created files and folders, while chmod sets permissions for files and folders that already exist.30 Dec 2020


    new file:   style.css

Changes not staged for commit:

    modified:   index.html

$ git stash
Saved working directory and index state WIP on main: 5002d47 our new homepage
HEAD is now at 5002d47 our new homepage

$ git status
On branch main
nothing to commit, working tree clean
Git branch
RELATED MATERIAL
Git branch
Read article
Bitbucket logo
SEE SOLUTION
Learn Git with Bitbucket Cloud
Read tutorial
At this point you're free to make changes, create new commits, switch branches, and perform any other Git operations; then come back and re-apply your stash when you're ready.

Note that the stash is local to your Git repository; stashes are not transferred to the server when you push.

Re-applying your stashed changes
You can reapply previously stashed changes with 

