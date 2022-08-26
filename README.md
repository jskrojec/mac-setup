## My Mac Setup

This repo contains info on all the apps I use on my mac. Setup inspired by [CodingGarden](https://coding.garden/).

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Homebrew/terminal/bash](#homebrewterminalbash)
  - [Homebrew](#homebrew)
  - [Terminal](#terminal)
  - [Shell](#shell)
  - [Install Bash and set it as the default](#install-bash-and-set-it-as-the-default)
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

```
brew install iterm2
```

Once installed, launch it and customize the settings / preferences to your liking. These are my preferred settings:

* Appearance
  * Theme
    * Minimal
* Profiles
  * Default
      * General -> Working Directory -> Reuse previous session's directory
      * Colors -> Basic Colors -> Foreground -> White
      * Text -> Font -> [Cascadia Code](https://github.com/microsoft/cascadia-code) or [Anonymous Pro](https://www.marksimonson.com/fonts/view/anonymous-pro)
          * I use this font in VS Code as well
      * Text -> Font Size -> 16
      * Keys -> Key Mappings -> Presets -> Natural Text Editing


### Shell

### Install Bash and set it as the default

## OS Productivity

### Window Management/Quick Launcher/Alt-Tab

### Dock/Finder

### Quick Launching

## Web Browser - Extensions and filters

## Node.js - nvm

## Code Editor - VS and VS Code

## Code Editor Extensions
