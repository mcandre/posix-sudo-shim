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

Some commands may break with `sudo`..., such as in Haiku nightly, where the underlying `su` may be broken. For such primarily single-user environments, a more reliable `sudo` shim would look like:

```sh
#!/bin/sh
# Assume root-level privileges and avoid PTY's
"$@"
```

# INSTALL

```console
$ git clone https://github.com/mcandre/posix-sudo-shim.git
$ cp posix-sudo-shim/lib/sudo /bin
```

# UNINSTALL

```console
$ rm /bin/sudo
```

# REQUIREMENTS

* [coreutils](https://www.gnu.org/software/coreutils/coreutils.html)

## Recommended

* [vast](http://github.com/mcandre/vast)
* [shfmt](https://github.com/mvdan/sh) (e.g. `GO111MODULE=on go get mvdan.cc/sh/v3/cmd/shfmt`)
* [bashate](https://pypi.python.org/pypi/bashate/0.5.1)
* [shlint](https://rubygems.org/gems/shlint)
* [checkbashisms](https://sourceforge.net/projects/checkbaskisms/)
* [ShellCheck](https://hackage.haskell.org/package/ShellCheck)
* [stank](https://github.com/mcandre/stank) (e.g. `go get github.com/mcandre/stank/...`)
* [slick](https://github.com/mcandre/slick) (e.g. `go get github.com/mcandre/slick/....`)

# DEVELOPMENT

## Lint

```console
$ vast [lint]
```
