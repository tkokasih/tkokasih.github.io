> IN PROGRESS

## Background

I worked with linux and docker container and I still have fuzzy understanding on what it is I'm typing to?
Like when I ssh into a server, or exec into a container, what is that prompt?
What is a shell? What's the difference between shell, tty, console, terminal, and cli?

## Shell

* There are many shells in Linux/Unix world: sh, bash, zsh, csh, ksh to mention a few
* There exists a POSIX standard for shell
  * If you want your script to be portable across shell, adhere to this standard
  * e.g. avoid "bashism" [tldp on portability](https://tldp.org/LDP/abs/html/portabilityissues.htm), [Ubuntu DashAsBinSh](https://wiki.ubuntu.com/DashAsBinSh)
  