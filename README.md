autovenv
==============================

## What

The idea is venv acts intuitively and smoothly, taking inspiration from git repositories. You don't type `source .git/bin/activate` and `deactivate` when changing between repos, do you?

It must do the following

- In a project dir with a `.venv` subdir, that `.venv` is automatically used.
- Navigate to a subdir in the project, original `.venv` is still used.
- When the project is left, the `.venv` is deactivate automatically.
- `.venv` in a nested project is used since it's "closer" to the working path

## Installation

Add this line to your `.bashrc` or profile:
    
```
source /path/to/.py_autovenv
```

Go to your project folder, run "virtualenv .venv", so your project folder
has a .venv folder at the top level, next to your version control directory.
For example:
.
├── .git
│   ├── HEAD
│   ├── config
│   ├── description
│   ├── hooks
│   ├── info
│   ├── objects
│   └── refs
└── .venv
    ├── bin
    ├── include
    └── lib

## Credits

Help in development process came from:
https://nolar.info/automatically-activate-virtualenv-on-cd/
https://gist.github.com/brianpkennedy/8943902