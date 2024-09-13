---
title: "lsdir - A Linux/Unix/MacOS `ls` Alias for Only Listing Directories"
description: "Create an alias for listing directories only using the unix/linux ls command"
date: 2024-09-13T18:48:28-07:00
draft: true
tags: ['bash', 'zsh', 'ls']
categories: ['programming']
references: []
---

## The Problem

When working in the terminal, you sometimes need to list only the directories in the current location. The standard `ls` command shows both files and directories, which can be overwhelming in cluttered directories.

The command for listing only directories in the current location is `ls -d */` which is not simple to remember, especially if it's not something that you do often.

## The Solution: lsdir

`lsdir`, an alias for only listing directories, which hopefully is easier to remember.
#### 1. Open your `.zshrc` or `.bashrc` file:

   For Zsh:
   ```
   vim ~/.zshrc
   ```

   For Bash:
   ```
   vim ~/.bashrc
   ```

#### 2. Click `i` on your keyboard to go into editing mode in `vim`

#### 3. Add the following line:
   ```
   alias lsdir='ls -d */'
   ```

#### 4. Save the file and reload your shell configuration:

   For Zsh
   ```
   source ~/.zshrc
   ```

    For Bash
    ```
    source ~/.bashrc
    ```

#### 5. Try it
    ```
    lsdir
    ```


You're done; Happy coding! 👾