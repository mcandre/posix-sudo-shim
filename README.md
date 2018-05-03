# posix-sudo-shim: a workaround for UNIX systems that lack full sudo

# EXAMPLE

```console
$ sudo echo 'all ur base r belong to us' >/flag.txt
$ cat /flag.txt
all ur base r belong to us
```

# ABOUT

posix-sudo-shim is a minimal drop-in replacement for [sudo](https://www.sudo.ws/), a full-feature elevated command execution system. posix-sudo-shim does not attempt to support the vast majority of sudo's many features, but rather provides minimal syntax and semantics support, in order to help in porting shell scripts between different UNIX systems, where sudo may not be present, but is called for by the scripts.

# NOTES

Some commands may break with `sudo`..., such as in Haiku nightly, where the underlying `su` may be broken.

# INSTALL

```console
$ git clone https://github.com/mcandre/posix-sudo-shim.git
$ cp posix-sudo-shim/lib/sudo /bin
```

# UNINSTALL

```console
$ rm /bin/sudo
```
