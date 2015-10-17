# How to:
##### Section Jumps
* [Save credentials](##save_your_credentials_in_Git)
* [Push to multiple repositories with one command](##push_to_multiple_repositories_with_one_command)
* [Sync with upstream branch]()

## Save your credentials in Git
### Temporary credential cache
1. Turn on the credential helper so that Git will save your password in memory for a while (default is 15 minutes).</br>
```$ git config --global  credential.helper cache```
* to change the default timeout period (setting is in seconds)</br>
```$ git config --global credential.helper 'cache --timeout=3600'```

### Permanent credential cache
Keep in mind this method stores your password on the disk in plain text
1. Add the following line to your ~/.netrc where "hostname" is the server's hostname, "username" and "password" are your credentials</br>
```machine <hostname> login <username> password <password>```
2. set restrictive filesystem permissions on that file:</br>
```chmod 600 ~/.netrc```

##### For Windows Machines
*untested*
1. open command prompt and type to create environment variable %HOME% where home will be set to 'C:\Users\"username"' </br>
```setx HOME %USERPROFILE%```
2. Go to C:\Users\"username" and create a file called _netrc
3. Add the following content (replace the <> with your values)</br>
```machine <hostname>
   login <username>
   password <password>```

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
