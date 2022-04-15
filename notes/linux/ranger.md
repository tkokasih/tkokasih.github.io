## Background

Having worked in linux for sometime, it is tiring to traverse directory structure with `cd` and `ls`.
There must be a better way.
And I have fascination with miller column.
So, I wish there is a terminal file manager that has miller column.

Lo and behold: `ranger`! And it already received the highest form of flattery: cloned project in other language.


## What is ranger?

One of plethora of file manager, written in python.
Prominent feature includes:
* Miller column!
* vi keybinding

Downside?
* People complain it is slow, but it is OK enough for me
* I still get my terminal went haywire if I tried to edit with vim from ranger.

## Some cheatsheet

Vim-like keybinding
```
Movement  (also commands that start with g)
  j, k    - move up/down the middle column
  h, l    - move in/out of the directory/file
  gg      - move to first entry
  G       - move to last entry

File manipulation   (also commands that start with y,d,p)
  cw      - change word, aka rename
  I       - rename, with cursor in the beginning of the filename
  A       - rename, with cursor in the end of the filename
  yy      - yank (copy) current selection
  pp      - paste
  dd      - cut current selection

Settings (starts with z)
  zh      - show hidden file
```

Further customization is possible with custom command.
But I haven't yet explored this.