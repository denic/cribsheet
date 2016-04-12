# Notes, cheats and tricks

Notes about programs I use.

- [Git](#git)

## Git

* show commits that are in the oldbranch but not yet in the new one
    * git log oldbranch ^newbranch --no-merges 

* Force git to clone with "https://" instead of "git://" urls 
  * git config --global url."https://".insteadOf git://

* Show diff of same file in different branches
  * git diff(tool) branch_a branch_b -- /path/to/file

* Reset all submodules (containing changes)
  * git submodule foreach git reset --hard



