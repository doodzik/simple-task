# About

Simple Task is a simple Todo list for the commandline.

# Installation

```
$ brew tap doodzik/tap https://github.com/doodzik/tap
$ brew instal simple_task
# if you use zsh run this to get the autocompletion
$ brew instal bash-completion
```


### configuration
```bash
# add this to your bashrc/zshrc
# add this if you use zsh
autoload bashcompinit
bashcompinit

EDITOR=vim # if you haven't set your editor set it
T_EXT=.txt
T_FILE="todo${T_EXT}" # default todo list
T_DIR=~/Library/Mobile Documents/com~apple~CloudDocs # path where the todos are saved to

complete -F _simple_task_complete simple_task
complete -F _simple_task_list_complete simple_task_list

alias t=simple_task
alias tl=simple_task_list
```

# Usage
## how to work on a specific task list

```bash
# add a todo, returns the task list
$ t hello world
todo
  1 hello world
# show tasks
$ t 
todo
  1 hello world
# remove/check a task by index, returns todo list, you can use tab-completion to get your tasks
$ t 1
todo
# access last removed tast
$ echo $T_LAST_DONE
hello world
```

## How to work with multiple task_lists

```bash
# change to a different task list if it isn’t present it creates a new one, prints content of the task list, you can use tab completion to access your task lists
$ tl tasks
tasks
# rename a task
$ tl tasks mv new_task_list
# edit task list file in editor
$ tl new_task_list o
# delete task list
$ tl new_task_list d
```
