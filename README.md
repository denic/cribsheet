# Notes, cheats and tricks

Notes about programs I use.

- [Git](#git)
- [Mongo DB](#mongo-db)
- [Ext JS](#ext-js)
- [Vim](#vim)

## Git

* show commits that are in the oldbranch but not yet in the new one
    * git log oldbranch ^newbranch --no-merges 

* Force git to clone with "https://" instead of "git://" urls 
  * git config --global url."https://".insteadOf git://

* Show diff of same file in different branches
  * git diff(tool) branch_a branch_b -- /path/to/file

* Reset all submodules (containing changes)
  * git submodule foreach git reset --hard

## Mongo DB

* Query for timespan
    *db.LogEntry.find({MachineName: /mono/, Message : /4188/,  TimeStamp : {$gt : new Date('2015-10-04T20:39:13.067Z')}}).sort({TimeStamp : 1})

## Ext JS

* Log ALL events of the selected compotent
    *Ext.util.Observable.capture(Ext.getCmp($0.id), function(evname) {console.log(evname, arguments);})

## Vim

* Close all buffers
    * http://stackoverflow.com/questions/3155461/how-to-delete-multiple-buffers-in-vim
        * :bd *.js <C-a>

* Yank into command line
    * http://stackoverflow.com/questions/3997078/how-to-paste-text-into-vim-command-line
      * <C-r> "
    
* Sort lines
    * Select lines in visual mode
    * :
    * :'<,'> sort u
    * http://vim.wikia.com/wiki/Sort_lines

* Interactive search and replace
    * %s/old/new/gc

* Jump to next matching character
    * f<character>

### Scroll up/down, keeping your cursor in its row

If you are in the middle of a file and want to scroll, but don't want to move your cursor all the way to the top row, use this:

  One line:

        Ctrl+Y → Move viewport down
        Ctrl+E → Move viewport up (Extra lines)

  Half a screen

        Ctrl+U → Move viewport Up
        Ctrl+D → Move viewport Down

                               
### Inner and outer select content by matching surrounding in Normal mode
    * vi' -> Matches the bla part of 'bla'
    * va{ -> Matches everything including the brackets in { foo: bar }

**Show all lines including the word under the cursor in the current file and it's includes**

    [I
    ]I -> limit the search to all lines following the cursor position
    [i -> List only the first occurency, useful for variable declaration lookup

