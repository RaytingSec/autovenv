autovenv
==============================

> Automatically activate and deactivate virtualenv as you change directories

## What

The idea is that venv acts intuitively and smoothly, taking inspiration from git repositories. You don't type `source .git/bin/activate` and `deactivate` when changing between repos, do you?

It must do the following:

- In a project dir with a `.venv` subdir, that `.venv` is automatically used.
- Navigate to a subdir in the project, original `.venv` is still used.
- When the project is left, the `.venv` is deactivate automatically.
- `.venv` in a nested project is used since it's "closer" to the working path

### Why not kennethreitz/autoenv

[autoenv by kennethreitz](https://github.com/kennethreitz/autoenv) works perfectly fine, but is not as streamlined. This script basically checks if `.venv` exists, whereas autoenv does that if you create a `.env` file specifying the current directory as a project to work on for an additional package virtualenvwrapper to interpret. And only then it activates but doesn't deactivate the virtualenv.

So it's a lot more complexity and dependencies for less functionality.

## Installation

Download the script, add to your `.bashrc` or profile, then restart your terminal session:

```
wget -O ~/.py_autovenv https://raw.githubusercontent.com/raydarnet/autovenv/master/.py_autovenv
echo "source ~/.py_autovenv" >> ~/.bashrc
source ~/.bashrc
```

Now you can go to your project folder, run `virtualenv .venv`, and navigate in and out of the directory, while the virtualenv is automatically activated and deactivated.

## Usage Guide

Ensure your virtualenv folders are named `.venv`. If choose a different name, specify in `venv_candidates()`

## Credits

Help in development process came from:
https://nolar.info/automatically-activate-virtualenv-on-cd/
https://gist.github.com/brianpkennedy/8943902