---
title: "Git: Case Sensitive File Renames"
tags:
  - evergreen
  - programming
  - productivity
  - git
draft: false
---
Certain operating systems, for example MacOS, are case **insensitive** in how they treat files. I.e. `test.txt` and `Test.txt` are equivalent. 

You can prove this by navigating around your file system in the terminal, pick a folder and use the incorrect casing to run the `cd` command.

```bash
cd dEsKToP
```
*It's not pretty but it does work*

---- 

This presents a problem for developers as the default setting for Git is to respect how the OS handles case sensitivity. This means renaming a file by running something like `mv Mycomponent.tsx Mycomponent.tsx` will not result in any case that is picked up by Git. 

To solve this you have 2 options.

## 1. Single File Rename: `git mv`

If you only need to rename a single file you can use the command:

```bash
git mv file.txt FileNewCasing.txt
```

If you forget and just run `mv <file> <FileNewCasing>` you can always run `git mv <file> <FileNewCasing>` later (because they're the same file to the OS remember).


## 2. Renaming Multiple Files

If you've gone on a spree of renames, and running `git mv` would now be impractical, you might want to blow away Git's tracking of your files and then re-add the renamed files back to be tracked.

```bash
git rm -r --cached . && git add .
```

**You may want to run these files separately to ensure you don't commit new files you don't yet want to be tracked.**
