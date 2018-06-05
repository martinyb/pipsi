# pipsi

pipsi = pip script installer

What does it do? pipsi is a wrapper around virtualenv and pip which installs scripts provided by python packages into separate virtualenvs to shield them from your system and each other.

In other words: you can use pipsi to install things like pygmentize without making your system painful.

How do I get it?

```bash
curl https://raw.githubusercontent.com/mitsuhiko/pipsi/master/get-pipsi.py | python
```

How does it work?

pipsi installs each package into `~/.local/venvs/PKGNAME` and then symlinks all new scripts into `~/.local/bin` (these can be changed by `PIPSI_HOME` and `PIPSI_BIN_DIR` environment variables respectively).

Compared to `pip install --user` each `PKGNAME` is installed into its own virtualenv, so you don't have to worry about different packages having conflicting dependencies.

Installing scripts from a package:

```bash
$ pipsi install Pygments
```

Installing scripts from a package using a particular version of python:

```bash
$ pipsi install --python /usr/bin/python3.5 hovercraft
```

Uninstalling packages and their scripts:

```bash
$ pipsi uninstall Pygments
```

Upgrading a package:

```bash
$ pipsi upgrade Pygments
```

Showing what's installed:

```bash
$ pipsi list
```

How do I get rid of pipsi?

```bash
$ pipsi uninstall pipsi
```

How do I upgrade pipsi? With 0.5 and later just do this:

```bash
$ pipsi upgrade pipsi
```

On older versions just uninstall and reinstall.
