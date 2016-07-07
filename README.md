# Bootstrapping a new machine

* Install `vcsh` and `myrepos`: `sudo aptitude install vcsh mr`.

* Pull the `mr` repository first:
```
vcsh init mr
vcsh mr remote add origin git@github.com:cunha/dotmr.git
vcsh mr pull origin master
vcsh mr branch --set-upstream-to=origin/master master
```

* Configure which repositories you want pulled to the new machine removing links from `.config/mr/config.d`. In particular, check whether you want `dotxfiles.git`.
  
* Pull all tracked repositories: `mr update`.  This will fail if you have some of the files that will be pulled in your home directory.  Simply delete the files and repeat `mr update`.

# Command reference

* Update all tracked repositories: `mr update`
* Check the status of repositories with: `vcsh status`, `mr update`
* Create a new repo: `vcsh init <repo>`
* Add, commit and push a new or changed file:
```
vcsh <repo> add <file>
vcsh <repo> commit -m 'message'
vcsh <repo> remote add origin <repo-github-address>
vcsh <repo> push -u origin master # -u makes local/master track origin/master
```

# Other commands to test

* `mr push`
