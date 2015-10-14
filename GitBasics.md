# Git Basics

## Structure and Workflow
The primary thing to remember about Git if you want things to go smoothly is that Git has three main states that your files can reside in:
* Committed - the data is safely stored in the local database
* Staged - the file has been marked in its current version to go into the next commit snapshot
* Modified - you have changed the file, but not commited it yet

Based on these 3 main states, there are three main sections of a Git project:
* The Git directory
    * this is where Git stores the metadata and object database for the project.
    * This is what is copied when you clone a repository from another computer
* The staging area
    * a file, generally contained in the Git directory, that stores information about what will go into your next commit. It is sometimes called the *index*
* The working directory
    * a single checkout of one version of the project.
    * these files are pulled out of the compressed database in the Git directory and placed on disk for you to use or modify

The workflow goes something like this:
1. You modify files in your working directory
2. You stage the files
3. you do a commit, which takes the files as they are in the staging area and stores that snapshot permanently to your Git directory
