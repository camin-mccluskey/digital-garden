---
title: Vim Commands I've Already Forgotten (Recipes)
tags:
  - programming
  - vim
  - productivity
  - sapling
drafts:
---
*This should not be treated as a comprehensive list of vim commands. Indeed it only scratches the surface and it's almost certainly only really useful for me (as these are the commands I frequently forget).*

# Vim Movements

## Jump to Last Changed

### Jump to Last Changed
`g;`
### Jump Forward Through the Change List
`g,`

## Cursor Movement and Positioning

### Center Cursor on Screen
`zz`

### Position Cursor on Top of Screen
`zt`

### Position Cursor on Bottom of Screen 
`zb`

### Move Screen Down One Page (Cursor to First Line)
`Ctrl+f`

### Move Screen Up One Page (Cursor to First Line)
`Ctrl+b`



# Finding and Replacing Text
## Add all results from Telescope to Quickfix List
From search results list `Ctrl+q` will add all results to QuickFix list.
## Find and Replace All text in Quickfix List
`:cfdo %s/<find>/<replace>/g`
## Find and Replace
### Current Line
`:s/foo/bar/g`
### All Lines
`:%s/foo/bar/g`
### All buffers
`:bufdo %s/pattern/replace/g`
### In Visual Selection
`:'<,'>s/foo/bar/g`



