
## Resources
- [Git](https://git-scm.com/)
- [GitHub](https://github.com/)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- ["Oh My GIT" Game](https://ohmygit.org/)
## "I don't GIT it!"
Git is a version control system that tracks and helps to manage changes in sets of computer files.  Originally authored by the legendary Linus Torvalds in 2005 to enable teams of any size to help contribute to the open source Linux kernel. This software would ultimately help accelerate adoption of git itself further than the Linux kernel. Today git, or the ideas it helped normalize in collaborative computing, can be observed across a wide variety of domains. 
Think of Git as a super-smart scrapbook for computer programmers. When programmers write code, they often need to make changes, try out new ideas, and collaborate with others without messing up the original work. Git helps them do all of this efficiently.

Git Provides the Following Functionality:
- Saving Progress: Imagine you’re working on a puzzle. Every so often, you take a picture of your progress. If you ever mess up, you can just look at a picture and put the pieces back exactly as they were in that snapshot. In Git, these snapshots are called "commits."

- Branching Out: Let’s say you want to try a new way of solving the puzzle without disturbing the layout you’ve already worked so hard on. You set up a new table and start assembling a different version based on one of your earlier pictures. In Git, this is called creating a "branch." It allows developers to work on new features or fix bugs without affecting the main project until they’re ready.

- Merging: Once you’re happy with your new solution on the second table, you can merge everything back onto the original table without losing any pieces. Git allows merging branches back into the main project, combining different changes smoothly.

- Checking History: If you ever need to see who added a piece and when, Git keeps a detailed log of who made what changes and when, just like a detailed journal for your project.

- Collaboration: Imagine you and several friends are working on different parts of the puzzle at different tables. Git helps everyone share their individual pieces, ensuring that all parts fit together perfectly in the end.

While git is a command line interface tool, which still looks straight out of a 1980s hacking scene, a strong ecosystems of web and desktop applications exist to support users at all levels of familiarity. Regardless of how you choose to interact with Git the capabilities of the program remain largely the same. With this guide you will finally "git gud" with all of them.

## Repositories

### What is a Repo?: 
A "repo" is short for repository. In the context of software development, a repository is a central place where data is stored and managed, typically code for a project. Repositories are used in version control systems like Git, which help manage changes to the code or documents.
### Creating a Repo Locally:
Initialize a git repo locally by invoking the 'init' command in the terminal: 
`git init`
### Cloning a Repo:
Typically a new directory is created to house the repo.
`git clone https://github.com/username/repository-name.git`
## Managing Changes to Files
### .gitignore:
A .gitignore file is used to specify intentionally untracked files that Git should ignore. These files are typically generated as part of the project build process, temporary files, or files containing sensitive information (like API keys, compiled binaries, or passwords) that should not be committed to version control.

### Staging Area
Sometimes referred to as the "index" or "cache." The staging area is where you can prepare changes before committing them to the repository.

Working Directory: This is where you make changes to your files. When you edit, add, or delete files, these changes are initially considered to be in the working directory.

Staging Area: When you're ready to commit your changes, you use the git add command to stage specific changes or files. Staging changes means that you're preparing them to be included in the next commit.

Repository (Commit History): Once you've staged the changes you want to commit, you use the git commit command to create a commit. The commit includes all changes currently in the staging area. After committing, the changes become part of the repository's history.

The staging area allows you to review and organize your changes before committing them. It gives you control over what changes you want to include in each commit, allowing you to create more granular and meaningful commit messages.

Imagine you're packing for a trip. Your working directory is like your home, where you gather all the items you might need for your trip. The staging area is like a suitcase, where you select and organize the specific items you want to take with you. And finally, the repository is like your destination, where your packed suitcase (commit) becomes part of your journey's history.

In summary, the staging area in Git serves as an essential tool for managing your changes and creating well-organized commits. It gives you the flexibility to review and select changes before they become part of your project's history.

## Cheat Sheet Contents

### SETUP
Configuring user information used across all local repositories

set a name that is identifiable for credit when review version history:
`git config --global user.name “[firstname lastname]”`

set an email address that will be associated with each history marker
`git config --global user.email “[valid-email]”`

set automatic command line coloring for Git for easy reviewing
`git config --global color.ui auto`

### Initialization
Configuring user information, initializing and cloning repositories

initialize an existing directory as a Git repository
`git init`

retrieve an entire repository from a hosted location via URL
`git clone [url]`

### Stage and Snapshot
Working with snapshots and the Git staging area

show modified files in working directory, staged for your next commit
`git status`

add a file as it looks now to your next commit (stage)
`git add [file]`

unstage a file while retaining the changes in working directory
`git reset [file]`

diff of what is changed but not staged
`git diff`

diff of what is staged but not yet committed
`git diff --staged`

commit your staged content as a new commit snapshot
`git commit -m “[descriptive message]”`

removes the file from the working directory and stages the removal of the file for the next commit
`git rm [file]`
### Branch and Merge
Isolating work in branches, changing context, and integrating changes

list your branches. a * will appear next to the currently active branch
`git branch`

create a new branch at the current commit
`git branch [branch-name]`

switch to another branch and check it out into your working directory
`git checkout`

merge the specified branch’s history into the current one
`git merge [branch]`

show all commits in the current branch’s history
`git log`


### SHARE & UPDATE
Retrieving updates from another repository and updating local rep

add a git URL as an alias
`git remote add [alias] [url]`

fetch down all the branches from that Git remote
`git fetch [alias]`

merge a remote branch into your current branch to bring it up to date
`git merge [alias]/[branch]`

transmit local branch commits to the remote repository branch
`git push [alias] [branch]`

fetch and merge any commits from the tracking remote branch
`git pull`














