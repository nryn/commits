# commits

## Purpose

commits is a command line tool for searching through 'karma' semantic commit message and co-authors.

You can find information about karma commits here: http://karma-runner.github.io/2.0/dev/git-commit-msg.html

The basic structure of a karma commit looks like this:

```
<type>(<scope>): <subject>

<body>

<footer>
```

And with a 'real' example:

```
refactor(deploy-script): Iterate over a list of tasks.

We don't need to repeatedly call the same functions. Cleaned up some indentation problems.

Co-authored-by: Narayan <nryn@example.com>
Co-authored-by: Buddy <buddy@example.com>
```

It can be used to display the scopes and types of recent commits, 

## Installation

To get set up, ensure you're in the root directory of this project.

Ensure the commits file is executable e.g. `chmod +x ./commits`

Ensure the commits file is in the PATH e.g. to add the project root to the path `export PATH=$PATH:$(pwd)`

## Usage

Without arguments, `commits` will show you the most recent unique scopes of commits in your current git repository.

Other usage instructions can be accessed by using the `-h | --help` flag.

`commits --help`

`commits` will only work in git repositories.
