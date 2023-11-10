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
  - [Window Management](#window-management)
  - [Quick Launching](#quick-launching)
  - [App Switching](#app-switching)
  - [Other Apps I Use Daily](#other-apps-i-use-daily)
- [OS Settings](#os-settings)
  - [Finder](#finder)
  - [Dock](#dock)
- [Menu Bar Customization](#menu-bar-customization)
  - [System Stats Widgets](#system-stats-widgets)
  - [Menu Bar Calendar](#menu-bar-calendar)
- [Web Browser - Extensions and filters](#web-browser---extensions-and-filters)
- [Node.js - nvm](#nodejs---nvm)
  - [Global Modules](#global-modules)
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
      - [Anonymice Nerd Font](https://www.nerdfonts.com/font-downloads)
      - [Caskaydia Cove Nerd Font](https://www.nerdfonts.com/font-downloads)
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

I store my `.bash_profile` on my private github repository so I can copy it over to any machine I'm setting up.

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

Or copy your '.gitconfig' from your '.dotfiles' private repository to your home directory:

```sh
curl -O [LINKHERE]
```

You can make a script to do that for you too!

## OS Productivity

### Window Management

I know this feature is built in to a lot of other operating systems, but it is not built in to a Mac, so we need an app for it.

You can use [rectangle](https://rectangleapp.com/) to move and resize windows using keyboard shortcuts.

I highly recommend installing this and memorizing the keyboard shortcuts. Fluid and seamless window management is key to being productive while coding.

```sh
brew install rectangle
```

### Quick Launching

The built in spotlight search has web search results as the default instead of apps or folders on my machine.

I use [Raycast](https://www.raycast.com/) to launch apps / folders.

### App Switching

The built in App switcher only shows application icons, and only shows 1 icon per app regardless of how many windows you have open in that app.

I use an app switcher called [Alt-Tab](https://alt-tab-macos.netlify.app/). It shows full window previews, and has an option to show a preview for every open window in all applications (even minimized ones).

I replace the built-in `CMD+TAB` shortcut with AltTab.

```sh
brew install alt-tab
```

### Other Apps I Use Daily

- [firefox-developer-edition](https://www.mozilla.org/en-US/firefox/developer/) - Preferred web browser
- [app-cleaner](https://freemacsoft.net/appcleaner/) - When removing an app, will search your file system for related files / settings that should be removed as well
- android-file-transfer - Transfer files to / from my android phone
- android-platform-tools - Installs `adb` without the need for the full android studio.
- [signal](https://www.signal.org/) - Messaging
- [discord](https://discord.com/) - Messaging / Community
- [vlc](https://www.videolan.org/) - I use VLC to watch videos instead of the built in QuickTime.
- [keka](https://www.keka.io/en/) - Can extract 7z / rar and other types of archives
- [kap](https://getkap.co/) - Screen recorder / gif maker
- [visual-studio-code](https://code.visualstudio.com/) - Code Editor

You can install them in one go by placing them all into a text file and then running brew install:

```sh
xargs brew install < apps.txt
```

## OS Settings

These are my preferred settings for `Finder` and the `Dock`.

### Finder

- Finder -> Preferences
  - General -> Show these on the desktop -> Select None
    - I try to keep my desktop completely clean.
  - General -> New Finder windows show -> Home Folder
    - I prefer to see my home folder in each new finder window instead of recent documents
  - Advanced -> Show all filename extensions -> Yes
  - Advanced -> Show warning before changing an extension -> No
  - Advanced -> When performing a search -> Search the current folder
- View
  - Show Status Bar
  - Show Path Bar
  - Show Tab Bar

### Dock

I don't use the Dock at all. It takes up screen space, and I can use Raycast to launch apps and AltTab to switch between apps. I make the dock as small as possible and auto hide it.

- System Preferences
  - Dock & Menu Bar
    - Size -> Small as possible
    - Position on screen -> Right
    - Automatically hide and show the Dock -> Yes

## Menu Bar Customization

### System Stats Widgets

I like to see my network traffic, CPU temp / usage and RAM usage at a glance.

I use [iStat Menus](https://bjango.com/mac/istatmenus/).

In each widget, a key setting to look for is under "widget settings", choose "merge widgets into one".

```sh
brew install istat-menus
```

### Menu Bar Calendar

I like to have a calendar in the menu bar that I can quickly look at. stats does not include one, so I found [itsycal](https://www.mowglii.com/itsycal/). It seems fine for my needs.

```sh
brew install itsycal
```

itsycal shows the date, so I hide the date in the system menu bar widget:

- System Preferences
  - Dock & Menu Bar
    - Clock
      - Show Date -> Never
      - Show Day of Week -> No

## Web Browser - Extensions and filters

I use [Firefox Developer Edition](https://www.mozilla.org/), because it is open source and comes from the Mozilla Foundation, a non profit company that respects my privacy. Check out [here](firefox-setup.md).

## Node.js - nvm

I use nvm to manage the installed versions of Node.js on my machine. This allows me to easily switch between Node.js versions depending on the project I'm working in.

See installation instructions [here](https://github.com/nvm-sh/nvm#installing-and-updating).

OR run this command (make sure v0.39.3 is still the latest)

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
```

After installation you'll want to add the following to your .bash_profile / .zshrc etc.

```sh
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```

Now that nvm is installed, you can install a specific version of node.js and use it:

```sh
nvm install 18
nvm use 18
node --version
```

### Global Modules

There are a few global node modules I use a lot:

- lite-server
  - Auto refreshing static file server. Great for working on static apps with no build tools.
- license
  - Auto generate open source license files
- gitignore
  - Auto generate `.gitignore` files base on the current project type

```sh
npm install -g lite-server license gitignore
```

## Code Editor - VS and VS Code

VS and VS Code is my preferred code editor.

Two of the most notable settings are:

```json
{
  "editor.linkedEditing": true,
  "editor.snippetSuggestions": "top",
}
```

- editor.linkedEditing
  - Automatically edit a closing tag when editing an opening tag
- editor.snippetSuggestions
  - Puts the most relevant auto complete options at the top

## Code Editor Extensions
