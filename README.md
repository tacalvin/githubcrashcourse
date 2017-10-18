# Github Crash Course
Git is a VCS(Version Control System) that allows for efficent collaboration for groups of people working on a project.

Projects are stored in repositories which can be started with the following command

~~~
git init
~~~

When you want to begin adding to the repository you will first add either new or modified files to be staged.


This is done with 
~~~
git add *filenames*
~~~

You can also verify which files that have had their changes accounted for with

~~~
git status
~~~

Once you have added your desired files you will than commit them with
~~~
git commit -m "Commit Message"
~~~
This will create a commit in the repo history with your changes and a message that should describe those changes

Once you are ready to finalize those changes, you will than push those changes to the main repository in which every can see them.

~~~
git push
~~~

Team mates can get an updated version by running
~~~
git pull
~~~
This will pull the latest version of the master repo
## Cloning
You can also clone a repository to a local copy with
~~~
git clone *repo address*
~~~

## Branching
Branching is a powerful concept that will allow someone to work on a seperate copy of a repository that will allow you to work on a special copy of the repo without intefering with other peoples work while you can just experiment.

In order to view existing branches you can use
~~~
git branch
~~~
In order to create a new branch you can use
~~~
git branch *branch_name*
~~~
To switch to a new branch you can use
~~~
git checkout *branch_name*
~~~

Once you have finished working on your changes to a specific branch you can then merge it back into the master branch

First you need to switch to the master branch
~~~
git checkout master
~~~

Than you can use
~~~
git merge *branch_name*
~~~
Which would be the branch you want to merge into the current branch

Afterwords you can delete the branch with 
~~~
git branch -d *branch_name*
~~~

## Reverting changes
If a mistake occurs you can go back to a specific commit with
~~~
git reset *commit_hash*
~~~
You can specify --soft, --hard, or --mixed modes which do the following
* soft will point the head of the repo to the commit specified but a commit at this point will push the changes up until the latest commit
* hard will change the actual history of the repo and modify files in your working directoy effectively erasing all commits past the specified one
* mixed will change the history to match to the specified commit but keep any changes in the working directoy effectively undoing a git add
