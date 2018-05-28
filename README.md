

# xml-authoring-project
A structured directory where we build and store xmls.

This acts as a project template which forms the base for creating an xml-authoring-directory for a particular client.

## Who needs this anyway?

So, you are a staff member who is responsible for editing a client's Xml files.

We have a client who wants some Xmls authored. We need to set up a folder on your computer that acts as a 'working directory' for the client's Xml project. 

We use Git SCM to track changes to the files within this directory.

Each instance of this [xml-authoring-project](https://github.com/forikal-uk/xml-authoring-project) has a `composer.json` file in the root directory which specifies an ever-increasing set of custom software tools that can speed up your most repetitive tasks.

### Custom software tools

These tools have been built to work in the context of this xml-authoring-project. 

We will use software tools to:

* to manipulate and query the Xmls files that are stored within this directory; 
* when run inside [Bitbucket Pipelines](https://bitbucket.org/product/features/pipelines), to test and report on the state of the Xml files whenever changes are committed.

We also use custom tools (along with the project's configuration settings) to convert the client's Google Sheets into snippets of Xml that are stored here. 

# Getting started

We assume that you have installed :

* [Git SCM](https://git-scm.com/) 
  * (with [Git LFS](https://www.atlassian.com/git/tutorials/git-lfs) enabled)
* [Composer](https://getcomposer.org/doc/00-intro.md) (installed globally)

## Navigate to your `Projects` directory

* On your workstation, open MacOs Terminal or Windows Git Bash
* Navigate to the folder on your computer where you keep Xml authoring projects. 
```
$ cd /Users/Bob/Documents/Projects/XmlAuthoring
```
* Determine the location of the "origin" Git repository for that client's working directory (ask the account manager).

Given a client, we may or may not already have their working directory set up.

### Using an existing working directory.

* Run `git clone` to get a local copy of the client's working directory
* Use `cd` to change into the working directory.
* Run `composer update` to ensure that all the dependent files are installed.

Now, you should be able to work on the Xml files.

Once your edits are finished, use `git` to [commit your changes](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository) to the `origin`.

### Set up a new xml authoring project working directory for a client

We create a new git repository (based on this [xml-authoring-project](https://github.com/forikal-uk/xml-authoring-project)), alter the remotes then push it to our git hosting solution. Effectively, we [fork it](https://help.github.com/articles/fork-a-repo/).

* Ensure the client has an empty "origin" Git repository created for them (ask the client's account manager).
* Run `git clone` to get a local copy of https://github.com/forikal-uk/xml-authoring-project 
* Use `cd` to change into the working directory.
* Use `git remote set-url` command set the `origin` to the client's repository. ie. 
```
$ git remote set-url origin git@github.com:path/to/git/repo.git
```
Query the setting to ensure it worked:
```
$ git remote -v
origin	git@github.com:path/to/git/repo.git (fetch)
origin	git@github.com:path/to/git/repo.git (push)
```
* `git push` to push the base project up to the client's `origin` repository.
* Run `composer update` to ensure that all the tools are installed.

Now, you should be able to work on the Xml files.

Once your edits are finished, use `git` to commit your changes to the `origin`.


# Using the tools

See: https://github.com/forikal-uk/xml-authoring-tools

# Keeping the tools updated

The custom tools are always improving. 

To update to the latest versions of the tools.

* First ensure all changes to client files are committed and pushed to the repository
* In the command terminal, navigate to the root of the client working directory and run `composer update`

