* Initialize the local directory as a Git repository.
```command
$ git init
```

* Add the files in your new local repository. This stages them for the first commit.
```command
# Adds the files in the local repository and stages them for commit.
# To unstage a file, use 'git reset HEAD YOUR-FILE'.
$ git add .
```

* Commit the files that you've staged in your local repository.
```command
# Commits the tracked changes and prepares them to be pushed to a remote repository.
# To remove this commit and modify the file, use 'git reset --soft HEAD~1' and commit and add the file again.
$ git commit -m "First commit"
```

* In the Command prompt, add the URL for the remote repository where your local repository will be pushed.
```command
# Sets the new remote ([remote name], [remote repository URL])
$ git remote add origin https://github.com/neth-insta/blabla.git

# Verifies the new remote URL
$ git remote -v
```

* Push the changes in your local repository to GitHub.
```command
# Pushes the changes in your local repository up to the remote repository you specified as the origin
$ git push origin master
```
