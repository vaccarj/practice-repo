## basic git commands

Following this tutorial: https://www.youtube.com/watch?v=RGOj5yH7evk&t=1608s. Includes instructions for setting up ssh keys, which are necessary for establishing a connection with the remote repository. 

Clone the repository into the local directory:
``` 
git clone git@github.com:username/repo-name.git
```

Confirm that git is working in the local repository:
```
ls -la
```
Should see a .git directory in the local folder, indicating git is working.

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
Note that you can include multiple messages like so: -m "message 1" -m "message 2"

Save the changes to the _remote_ repository where the project is hosted:
``` 
git push origin main
```
Origin represents the location of the remote git repository. Main in this case is the branch we want to push to.
