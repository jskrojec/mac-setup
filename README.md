# My Mac Setup

This repo contains info on all the apps I use on my mac. Setup inspired by [CodingGarden](https://coding.garden/).

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Homebrew/terminal/bash](#homebrewterminalbash)
  - [Homebrew](#homebrew)
  - [Terminal](#terminal)
  - [Shell](#shell)
  - [Install Bash and set it as the default](#install-bash-and-set-it-as-the-default)
    - [Customizing Bash with `.bash_profile`](#customizing-bash-with-bash_profile)
    - [Commands used by my .bash_profile](#commands-used-by-my-bash_profile)
    - [Install the latest version of git](#install-the-latest-version-of-git)
- [OS Productivity](#os-productivity)
  - [Window Management/Quick Launcher/Alt-Tab](#window-managementquick-launcheralt-tab)
  - [Dock/Finder](#dockfinder)
  - [Quick Launching](#quick-launching)
- [Web Browser - Extensions and filters](#web-browser---extensions-and-filters)
- [Node.js - nvm](#nodejs---nvm)
- [Code Editor - VS and VS Code](#code-editor---vs-and-vs-code)
- [Code Editor Extensions](#code-editor-extensions)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Homebrew/terminal/bash

### Homebrew

[Homebrew](https://brew.sh/) allows us to install tools and apps from the command line.

To install it, open up the built in `Terminal` app and run this command:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

This will also install the xcode build tools which is needed by many other developer tools.

After Homebrew is done installing, we will use it to install everything else we need.

### Terminal

The first app I install is to replace the built in `Terminal`.

Documentation for more info on what iTerm2 can do: [https://iterm2.com/documentation.html](https://iterm2.com/documentation.html)

We install this using a Homebrew "cask". Casks are full applications, similar to what you would install from the App store.

```sh
brew install iterm2
```

Once installed, launch it and customize the settings / preferences to your liking. These are my preferred settings:

- Appearance
  - Theme
    - Minimal
- Profiles
  - Default
    - General -> Working Directory -> Reuse previous session's directory
    - Colors -> Basic Colors -> Foreground -> White
    - Text -> Font -> [Anonymous Pro](https://www.marksimonson.com/fonts/view/anonymous-pro)
    - Text -> Font Size -> 16
    - Keys -> Key Mappings -> Presets -> Natural Text Editing

### Shell

Mac now comes with `zsh` as the default [shell](https://en.wikipedia.org/wiki/Comparison_of_command_shells). `bash` is my preferred shell.

If you're going to stick with `zsh`, checkout [Oh My Zsh](https://ohmyz.sh/) which gives you a bunch of customizations out of the box.

### Install Bash and set it as the default

To see what shell is currently your default, run:

```sh
echo $SHELL
```

To install the latest version of bash:

```sh
brew install bash
```

Then, determine where bash got installed:

```sh
which bash
```

This will likely print `/opt/homebrew/bin/bash`.

We now need to add this to our `/etc/shells` file so we can set it as our default shell.

Open up the `/etc/shells` file in `nano` (a command line text editor) with super user privileges (you will need to type your password after running this command):

```sh
sudo nano /etc/shells
```

Command explained:

- [`sudo`](https://en.wikipedia.org/wiki/Sudo) is a way of running a command with `super user` privileges.
- [`nano`](https://en.wikipedia.org/wiki/GNU_nano) is an easy to use command line editor. As opposed to [`vi` or `vim`](https://en.wikipedia.org/wiki/Vim_(text_editor)).
- `/etc/shells` is the file we need to edit / update.

This will launch a command line editor. Add `/opt/homebrew/bin/bash` to the file above the other list of shells.

Press `CTRL+X` to close the file and then `Y` to confirm / save the changes.

Now that `/opt/homebrew/bin/bash` is in our `/etc/shells` file, we can set it as our default shell (you will need to enter your password for this command as well):

```sh
chsh -s /opt/homebrew/bin/bash
```

Now that you've changed your shell, if you open up a new iTerm2 tab or close / re-open iTerm2, you should be presented with a `bash` shell!

You can run the following to confirm you shell has changed:

```sh
echo $SHELL
```

#### Customizing Bash with `.bash_profile`

I store my `.bash_profile` on [github here](???) so I can copy it over to any machine I'm setting up.

Copy this file (or create your own) in your home directory:

```sh
cd ~
curl -O [LINKHERE]
```

#### Commands used by my .bash_profile

- vcprompt - list the current branch if in a folder that is a git repo

```sh
brew install vcprompt
```

#### Install the latest version of git

Use brew to install the latest version of `git`:

```sh
brew install git
```

Open a new tab / window to start using the latest version:

```sh
git --version
```

Configure git with your name / email and preferred editor:

```sh
git config --global user.name [name]
git config --global user.email [email]
git config --global core.editor nano
```

## OS Productivity

### Window Management/Quick Launcher/Alt-Tab

### Dock/Finder

### Quick Launching

## Web Browser - Extensions and filters

## Node.js - nvm

## Code Editor - VS and VS Code

## Code Editor Extensions
