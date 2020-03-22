# Harmony
 > A tool to sync shell history across system

Note: This tool only supports ZSH for now. Bash support will be added soon!

### Installation

If you have go language installed on your system

```shell script
go get https://github.com/BharatKalluri/harmony
```

create a directory to store harmony config

```shell script
mkdir -p ~/.config/harmony/
```

and create a file called config which contains the github token and shell history path
, here is how a sample config file would look

```shell script
$ cat ~/.config/harmony/config
GITHUB_TOKEN=<your github token>
SHELL_HISTORY_PATH=/Users/bharatkalluri/.zsh_history
```

> Instructions for how to get a github token can be found
> [here](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line), 
> Make sure you select the "gist" checkbox on the permissions page. 

### Run

Harmony uses [secret gists](https://help.github.com/en/enterprise/2.13/user/articles/about-gists) 
as a data store. Every time the command is run, it either updates the gist or updates the local shell history
by looking at which one was updated the latest.

To sync your history, just run
```shell script
harmony
```

and it should automagically make sure all your shell history is in sync!