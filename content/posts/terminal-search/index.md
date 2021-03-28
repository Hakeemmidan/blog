---
title: "Stop Arrowing Up So Much In Terminal; Search Instead! (Linux/Unix)"
description: "Stop arrowing up in terminal so much. Search instead! (Linux/Unix)"
date: 2020-12-31T19:01:40+03:00
draft: false
tags: ['terminal']
categories: ['programming']
references: ["'Red Hat System Administration I' Student Workbook (ROLE)"]
---

## Problem
Do you ever *NOT* feel like re-writing a command that you wrote some N commands ago?
I do!

Arrowing up and focusing until you reach what you want can be annoying for an efficient 
programmer. Although it usually only takes a couple of seconds, it still adds up. Plus, 
you don't want to waste your brainpower on such a task (unless you like doing it).

One of the best pieces of advice I heard when I first started programming is:
> "Always improve/automate tasks that you know you're going to continuously repeat in the future"

So let's do that. Let's improve this situation.

## Solution

#### Ctrl+r

This does a 'reverse-i-search' or 'bck-i-search', which finds the most recent closest match.

`Ctrl+r` again to go to next match (further back in history).

{{< figure
src="ctrl-r.png"
link="ctrl-r.png"
alt="Ctrl+r keyboard shortcut example use"
attr="Ctrl+r keyboard shortcut example use"
width="400"
class="center"
>}}

It searches through an environment variable called `$HISTFILE`. The number of commands that 
this file remembers depends on your `$HISTSIZE`.

I believe the default `$HISTSIZE` in Unix/Linux is around 500. You can check yours by running:
```Bash
$ echo $HISTSIZE
```

____

#### Alternative approach
```Bash
$ history 0
  0 echo 'example command 0'
  1 echo 'example command 1'
  2 echo 'example command 2'
  3 echo 'example command 3'
  ...
```

This displays your history from 0 to `$HISTSIZE`.

You can either scroll or `Cmd+f` to find your command.
To execute the command, run:

```Bash
$ !<command-number>
```
... where `command-number` is the number displayed leftmost to your selected command.

{{< figure
src="history.png"
link="history.png"
alt="'history 0' command example use"
attr="'history 0' command example use"
width="500"
class="center"
>}}

Happy coding!