## What is ranger?

One of plethora of file manager, written in python.

## What's so special about ranger?

* It implements Miller Column
* With vi keybinding

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