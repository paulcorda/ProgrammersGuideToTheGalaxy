# Linux Enhancements

## Show git branch in terminal
Add the following to ```~/.bashrc```:

```
# Add git branch if its present to PS1
parse_git_branch() {
 git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[01;31m\] $(parse_git_branch)\[\033[00m\]\$ '
```

## Fix vim compatibility
Add the following to ```~/.vimrc``:

```
set nocompatible
```
