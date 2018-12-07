# commits

## Purpose

commits is a command line tool for searching through 'karma' semantic commit messages and co-authors.

It can be used to display the scopes and types of the most recent commits, as well as co-authors who worked/paired/mobbed on the commits, and can count these things.

## Installation

To get set up, ensure you're in the root directory of this project.

Ensure the commits file is executable e.g. `chmod +x ./commits`

Ensure the commits file is in the PATH e.g. to add the project root to the path `export PATH=$PATH:$(pwd)`

## Usage

`commits` will only work in git repositories.

Without arguments, `commits` will show you the most recent unique scopes of commits in your current git repository. An example for this repository:

```
$ commits
help 
alphabetical-sorting 
sort-authors 
readme 
commits-script
```

You can ask for the types of commits, and for a count to be displayed:

```
$ commits --type --count
   5 feat 
   2 refactor 
   2 docs 
   1 chore  
```

Other usage instructions can be accessed by using the `-h | --help` flag.

```
$ commits --help

A tool to search karma commits and co-authors.

Usage: commits [options]
Options:

	-a, --all
		Include all commits, rather than the default of 6 weeks.
	-s, --search <string>
		Filter results to match on the given string.
	-t, --types
		Show a table of karma commit type usage.
	-u, --authors
		Show a list of co-authors/contributors. Cannot be used with the -t | --type flag.
	-p, --prefix
		May only be used in conjunction with the -u | --authors flag. Will print authors with a "Co-authored-by:" prefix.
	-c, --count
		Prints results with usage counts. Will override usage of the -p | --prefix flag when used alongside -u | --authors.
	-az, --sort
		Alphabetically sort results. Without this, the results are sorted by the most recent, descending.
```

## What's a "Karma commit"?

It's semantics for your git commits. You can find information about karma commits here: http://karma-runner.github.io/2.0/dev/git-commit-msg.html

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
