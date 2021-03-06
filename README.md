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

#### Show Commit Log

    git log < --pretty >

#### Review Stage Files

    git diff --cached

#### Revert File Version
    git checkout <version_number> <path_to_file>

#### Squashing Commits
Edit whatever appears in your editor, replace 'pick' with 'squash'. At least one 'pick'

    git rebase -i HEAD~(number of commits) ex: git rebase -i HEAD~4

#### Resetting Author Name
    git commit --amend --author <author name> ex: 'Ricky Hurtado and Ace Subido <dev+ricky+ace@aelogica.com>'

#### Rebase the Local Branch Using the Master Branch
First, update the master

    git pull origin master

Second, checkout to your local branch and do rebase

    git checkout <local branch>
    git rebase master

#### Compare and Add Files for Commit
Make sure to double check the changes done before committing. As much as possible, commit related files.

    git add -p

## Server Monitoring
    ssh <username>

#### Monit
    watch 'sudo monit summary'

## Redis
Running the redis server

    redis-server

## Resque and Scheduler
Run resque

    rake environment resque:work QUEUE=* (* for all or specify the value Ex. high) < VERBOSE-1 > < --trace >

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

#### Kill Running Rails Services

    lsof -wni

or with filter

    lsof -wni tcp

and filter with specific port

    lsof -wni tcp:3000

#### Display All Dirs in Tree

    ls -R | grep ":$" | sed -e 's/:$//' -e 's/[^-][^\/]*\//--/g' -e 's/^/   /' -e 's/-/|/'

#### Quick Command

    git pull origin master && bundle && RAILS_ENV=production bundle exec rake db:migrate assets:precompile && ps -ef | grep unicorn

## VIM with YADR Commands

#### Show Directory Tree

    :NERDTree

#### Divide Selected Screen Horizontally

    SS

#### Divide Selected Screen Vertically

    VV

#### Move Cursor At The End

    Shift+$

#### Move Cursor At The Beginning

    Shift+^

#### Move Cursor At The Top

    GG

#### Move Cursor At The Bottom

    Shift+G

#### Show the GIT Commits History

    :Gblame

#### Find Files

    ,T

#### Find in Files

    ,GG

#### Search in Current File

    /

#### Search Next

    CTRL+N

#### Search and Replace

    :%s/find text/text as replacement/g

#### Copy to Clipboard
Use HJKL keys to highlight the text

    Shift+V, Shift+", Shift+*, Y

#### Paste from Clipboard

    I, CMD+V

#### Paste from Copied Highlighted Text (external file)

    :set paste

Then turn off paste

    :set nopaste

#### Hide and Show Line Numbers

    :set nonumber
    :set number

#### Jump To Specific Line Number

    :line_number

#### Highlight and Replace Text (same column)

    :CTRL+V
    (use HJKL to highlight text)
    press small 'C'
    type the text as replacement
    ESC

#### Move Cursor to the Next Pane

    CTRL+WW

#### Comment Out Highlighted Code Line(s)

    gcc

#### Place the cursor on specific character

    Example string [STRING] [string]
    press small 'F' key then the character
    (With the example above considering the cursor is on the 'E' of 'Example string...', if I press small 'F' then '[', the cursor jumps to the first '[' but if I press 2 then small 'F' then '[', the cursor jumps to the second '['. Therefore, pressing number key first tells the position of the selected character. Pressing 'Shift+F', cursor jumps backwards.)

    press small 'F' key then the character then followed by ';', cursor finds the next position of the charcter

## Links

#### YADR
<http://blog.aelogica.com/tutorial/yadr-yet-another-dotfile-repo/>
<https://github.com/skwp/dotfiles>

#### MiniTest
<https://github.com/seattlerb/minitest>
<http://mattsears.com/articles/2011/12/10/minitest-quick-reference>
<http://www.littlelines.com/blog/2013/12/17/a-guide-for-writing-maintainable-rails-tests/>

#### MacVim
<http://vim-adventures.com/>
