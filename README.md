## basic git commands

Following this tutorial: https://www.youtube.com/watch?v=RGOj5yH7evk&t=1608s. Includes instructions for setting up ssh keys, which are necessary for establishing a connection with the remote repository. 


Clone the repository into the local directory:
``` 
git clone git@github.com:username/repo-name.git
```

Confirm that git is working in the local repository:
```
ls -la
> .git # you should see this directory in the local folder, indicating git is working
```

As you work, check file statuses. Will show you modified and untracked files.
```
git status
```

Tell git which files you want to track
```
git add . # track all files in the directory
git add filename # track just this file
```

Commit the changes to the _local_ repository, including a message:
```
git commit -m "Updated README.md"
```

Note that you can include multiple messages like so: 
```
git commit -m "Message 1" -m "Message 2"
```

You can also add and commit changes at once using
```
git commit -am "Message"

Save the changes to the _remote_ repository where the project is hosted:
``` 
git push origin main
```
Origin represents the location of the remote git repository. Main in this case is the branch we want to push to.

Made a mistake? To undo an add, use
```
git reset filename
```

To undo the most recent commit, point the HEAD one step back to the previous commit:
```
git reset HEAD~1
```

To reset back to a particular commit, use
```
git log # find the hash of the commit you want
git reset hash
```
This will unstage all commits after the hash. Using git reset --hard will completely remove the unstage commits.


## branching tutorial

View branches that currently exist:
```
git branch
```
The branch with the star next to it is the one you are currently on.

Create a new branch called "feature". The -b tells it you are creating the branch. Checkout is used to switch to a different branch.
```
git checkout -b new-branch-name
```

Then do the usuals, edit files, etc:
```
git add .
git commit -m "Message"
```

How does the current branch differ from main?
```
git diff
```

Push changes to the new branch in the remote repository:
```
git push origin feature
```

As you're working on your new branch, you can pull updates from main into the new branch using
```
git merge main
```
(though you might need to resolve conflicts)

It's easiest to merge branches and resolve conflicts on the github interface or directly in the code. After that, if you would like to see the updates to main in the local repository, use:
```
git pull origin main
```

To delete a branch after you merge:
```
git branch -d branch-name
```

