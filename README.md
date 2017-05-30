autovenv
==============================

> Automatically activate and deactivate virtualenv as you change directories

## What

![Demonstration](demo.gif)

The motivating idea is that venv should act automatically, taking inspiration from git repositories. You don't type `source .git/bin/activate` and `deactivate` when changing between repos, do you?

So, this script does the following:

- Navigate to a project dir with a `.venv` subdir, and that `.venv` is automatically used.
- Navigate to a subdir in the project, original `.venv` willl still be used.
- When the project is left, the `.venv` is deactivate automatically.
- `.venv` in a nested project is used since it's "closer" to the working path

### Why not kennethreitz/autoenv

[autoenv by kennethreitz](https://github.com/kennethreitz/autoenv) works perfectly fine, but is not as streamlined. This script basically checks if `.venv` exists, whereas autoenv does that if you first create a `.env` file specifying the current directory as a project to work on using `workon` from virtualenvwrapper (you also have to install that as well). And only then it automatically activates, but doesn't deactivate the virtualenv.

So it's a lot more complexity and dependency for less functionality.

## Installation

Download the script, add to your `.bashrc` or profile, then restart your terminal session. The following works in a plain Ubuntu installation, but may need modifications for your system.

```
wget -O ~/.py_autovenv https://raw.githubusercontent.com/raydarnet/autovenv/master/.py_autovenv
echo "source ~/.py_autovenv" >> ~/.bashrc
source ~/.bashrc
```

Now you can go to your project folder, and your virtualenv is activated automatically! Or if not created yet, run `virtualenv .venv` to create the virtualenv, afterwards it'll be detected and activated automatically.

## Usage Guide

Ensure your virtualenv folders are named `.venv`. If choose a different name, specify in the script's `venv_candidates()` function.

## Credits

Help in development process came from:

- https://nolar.info/automatically-activate-virtualenv-on-cd/
- https://gist.github.com/brianpkennedy/8943902
