This repository contains some useful and documented pre-commit hooks to use with git.

## Included hooks

hook | description
------------ | -------------
pre-commit | Allow to run multiple pre-commit hooks as specified in the script.
pre-commit-compile | Compile the project and abort commit if it fails.
pre-commit-default | The default git pre-commit hook checking for example for trailing whitespaces.
pre-commit-uncrustify | Run [Uncrustify](http://uncrustify.sourceforge.net/) on your sourcefiles and abort the commit if style violations have been detected. Generate a patch to fix these violations.

## Features

* Shell agnostic, should work with any Posix compliant shell
* Robust against whitespaces and special characters in file names and directories
* Tested on Linux and Mac OS

## Example

Everything is explained more easily with a few pictures. For example the [Uncrustify](http://uncrustify.sourceforge.net/) hook.

* Add or edit a file and work on some code

![Work on code](example_pictures/work_on_code.png)

* Add changes

![Add changes](example_pictures/add_file.png)

* Attempt to commit changes

![Commit changes](example_pictures/commit_changes.png)

* Apply the automatically created patch to fix the formatting

![Apply patch](example_pictures/apply_patch.png)

* Commit again

![Commit changes again](example_pictures/commit_changes_again.png)

## Installation

1. Clone the repository

```
git clone git://github.com/githubbrowser/Pre-commit-hooks.git
```

2. Every script has a section named `CONFIGURATION` at the top. Here you will find relevant configuration options. Update the configuration section in `install_hooks.sh` with the hooks that you want to install.

3. Copy the pre-commit hooks into your repository. Note that the script will ask before overwriting any existing hooks.

```
./install_hooks.sh /path/to/repository
```

4. The pre-commit hooks live in the `.git/hooks` subdirectory of your git repository. Update their configuration sections if required and you are good to go. By default the hooks will abort the commit and print a notice if any required configuration is missing.

5. Work on your code as usual and the hooks should be run automatically when calling `git commit`.

6. Profit!
