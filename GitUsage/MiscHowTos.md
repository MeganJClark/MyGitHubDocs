# How to:
##### Section Jumps
* [Push to multiple repositories with one command](##push_to_multiple_repositories_with_one_command)
* [Sync with upstream branch]()

## Push to multiple repositories with one command
1. Use && to push to both repositories</br>
```$ git push first-remote && git push seond-remote ```
2. Configure a repository with multiple repo addresses
    * create an "all" repository that will hold all the repo addresses, starting with the addres you want to use for both fetch and push</br>
    ```$ git remote add all repo-1-address```
    * Add another push address to "all"</br>
    ```$ git remote set-url --add all repo-2-address```
    * verify that "all" contains necessary addresses</br>
    ```$ git remove -v show```
    * when you push, push "all"</br>
    ```$ git push all```

## Sync with upstream branch
1. change to current working directory using terminal or command prompt
2. Fetch the upstream repository</br>
```$ git fetch upstream```
3. check out your fork's local master branch</br>
```$ git checkout master```
4. Merge changes from upstream into local master (*don't worry you won't lose local changes*)</br>
```git merge upstream/master```
5. Push
