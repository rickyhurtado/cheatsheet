# IRONCODER CHEAT SHEET

## GIT
#### Status
    git status

#### Cloning Project
    git clone <git_repo> <directory>
    git remote rename <old> <new> Ex: git remote rename origin new_name

#### Check Remote Repo
    git branch -r

#### Check Local Repo
    git branch -v

#### Fetch and update local branch
    git checkout <local_branch_to_update>
    git merge --no-ff <remote_repo_alias>/<local_branch_to_update>

#### Merge Local Branches
    git checkout <parent_local_branch>
    git merge --no-ff <child_local_branch> OR
    git merge --no-ff feature/<child_local_branch>

#### Fetch, Merge Remote and Local Branches, and Push
If push fails, do the first two commands
    git fetch --all
    git merge --no-ff <remote_alias>/<local_branch> <local_branch> *good practice*
    git push <remote_name> <local_branch> 

#### Create Branch Feature
    git checkout dev
    git checkout -b feature/<child_local_branch> <parent_local_branch>

#### Delete Branch
    git branch -d <local_branch>
    git branch -D <local_branch> (force delete)

#### Soft Reset (undoing the commits)
    git reset --soft HEAD^ or <specify the commit number>

#### Hard Reset (Delete all the changes including the codes/files)
    git reset --hard HEAD^ or <specify the commit number>

#### Clean Up Remote Branches from Local Computer
    git fetch origin --prune

#### Stash
    git stash
    git stash list
    git stash apply
    git stash pop (apply and delete stash)
    git stash drop
    git stash clear

#### Revert File Version
    git checkout <version_number> <path_to_file>

#### Squashing Commits
Edit whatever appears in your editor, replace 'pick' with 'squash'. At least one 'pick'

    git rebase -i HEAD~(number of commits) ex: git rebase -i HEAD~4


#### Resetting Author Name
    git commit --amend --author <author name> ex: 'Ricky Hurtado and Ace Subido <dev+ricky+ace@aelogica.com>'

## Server Monitoring
    ssh <username>

#### Monit
    watch 'sudo monit summary'

## Redis
Running the redis server

    redis-server

## Resque and Scheduler
Run resque

    rake environment resque:work QUEUE=* (* for all or specify the value Ex. high)
    --trace (add this - optional)
    VERBOSE-1 (add this - optional)

Run scheduler

    rake environment resque:scheduler QUEUE=high (or * for all - same as above)
    
## Unix

#### Copy SSH Public Key

    pbcopy < ~/.ssh/id_rsa.pub

From VM, edit the authorized_key file

    vi ~/.ssh/authorized_keys

then press

    Command+B

then press

    :wq