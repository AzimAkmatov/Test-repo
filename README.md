# bashy

NOTE **Bashy is incompatible with zsh**

On new Macs running Big Sur, Monterey, or Ventura, change your shell from default `zsh` to `bash`:

```sh
chsh -s /bin/bash
``````

Repo for all of our custom `bash` command line applications

## Prerequisites (Only for Data Engineers)

1. You'll need to get the `ch-nextgen.pem` file from someone on the Engineering team. Make sure
   it's saved in your `~/.ssh` directory with a `0600` permission. See below:

```sh
$ chmod 0600 ~/.ssh/ch-nextgen.pem
$ ls -la ~/.ssh/ch-nextgen.pem
-rw-------@ 1 wes  staff  1692 Sep 19  2017 /Users/wes/.ssh/ch-nextgen.pem
```

2. Contact @wbailey to ensure your working IP address is whitelisted to use any of the AWS services:

## Installation

1. Clone the repo

```sh
git clone git@github.com:carrumhealth/bashy.git
```

2. Install the command line tool

```sh
cd $CARRUM_HOME/bashy
make install
```
### Installation details:
Bashy is a shell based tool that has responsibilities for assisting in environment setup, maintenance, and development. It is essential for Carrum Health engineers


The "make install" command performs the following tasks:

**-Installs Homebrew on macOS**

**-Installs Docker on macOS**

**-Backs up existing bash files**

**-Copies the source files to set up bashy itself**


### Note:

"**make install**" conditionally installs CH environment only for MacOS.
For Ubuntu OS run:

```sh
cd $CARRUM_HOME/bashy
make install-ubuntu
```

3. Open a new terminal window

4. See the [Quick Start Guide](docs/quick-start-guide.md).

## Uninstall bashy

```sh
cd $CARRUM_HOME/bashy
make uninstall
```

## For [Developers](docs/developer.md)


## Updating Versions

The only difference from installing is to update the repo instead of cloning.

## Release Notes

Review the following notes for all of the new features and summary of the changes

- [Release 58.4](docs/releases/58.4.md)

- [Release 58.3](docs/releases/58.3.md)

- [Release 58.2](docs/releases/58.2.md)

- [Release 58.1](docs/releases/58.0.md)

- [Release 58.0](docs/releases/58.0.md)

- [Release 57.0](docs/releases/57.0.md)

- [Release History](docs/releases)

## Tools

### ch

The `ch` command is a general purpose command that provides access to all Carrum Health AWS hosted
infrastructure git repo management. Use this to connect to an instance and access files securely.

[Shortcuts](docs/ch-shortcuts.md)

### h

The `h` command sits on top of the `heroku` command providing shorthand notation for many commands
that require both application and organization specification. It also provides methods to perform
common tasks for our applications such as deployment and command line database access:

[Shortcuts](docs/h-shortcuts.md)

### s

The `s` command provides access to our slack channels. The functions behind it can be used to
automate messaging to the _technology_ channel for notification purposes:

[Shortcuts](docs/s-shortcuts.md)

### Other Aliases & Shortcuts

[Git Shortcuts](docs/git-shortcuts.md)

[NPM Shortcuts](docs/npm-shortcuts.md)

[Handy Shortcuts](docs/handy-shortcuts.md)

See the `ch` command for other operations on all Carrum Health repositories.

## Colors

With the release of Bashy 37.0 we now have access to terminal colors. This is part of the CLI
capability of the `ch` command:

```sh
17:42 $ ch cli help

Usage: ch cli [args]
  help                       - This usage message
  colors:list                - Display the defined environment variables and supported colors
  usage [text]               - Standard format for command help usage
  installed                  - Indicate installation is complete
  complete                   - Indicate process is complete
  title [text]               - Title format for the text
  red [text]                 - Format text in red
  red:bold [text]            - Bold face the text in red
  out [text] [color=blue]    - Colored format output of the text
  bold [text] [color=blue]   - Bold face colored format output of the text

NOTE: There are function shortcuts for all supported colors.  Red is illustrated for brevity

```

## Custom Configuration

Bashy is extensible. It will overwrite the host's `~/.bash_profile`. To extend or overwrite any
bashy functionality, create `bash_profile-bashy-custom` and/or `bashrc-bashy-custom` files. Both
are sourced toward the end of the `bash_profile`.

## Troubleshooting

After MacOS update port 5000 will not be available for one of CH services.
To solve this problem:
1. Open "System Settings" on the Top-Left corner of your display.
2. Open "General"
3. Open "AirDrop & Handoff"
4. Turn off "Allow Handoff between this Mac and your iCloud devices"

### For any other issues contact the OPS team.
