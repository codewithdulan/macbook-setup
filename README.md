## My Mac Setup

Welcome to my MacBook setup! In this README.md file, I'll walk you through the tools, applications, and configurations I use to make my MacBook a productive and efficient machine. Whether you're a fellow Mac user looking for inspiration or just curious about my setup, I hope you find this information helpful.

## What Macbook do I have?

I am now using the Macbook Pro.

These are the specs at a glance:
* Apple M2 Pro
* 16GB RAM
* 500GB SSD


## Homebrew / Terminal / Shell

### Homebrew
[Homebrew](https://brew.sh/) is a popular package manager for macOS and Linux operating systems. It allows users to easily install, update, and manage a wide variety of software packages and libraries from the command line.

#### Installation

To get started with Homebrew, follow these simple steps:

1. **Open Terminal:** Launch the Terminal app on your macOS or Linux system. This is where we'll run the installation command.

2. **Run the Installation Command:** Copy and paste the following command into your Terminal and press Enter:

    ```sh
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

   This one-liner script will download and install Homebrew on your system. It may prompt you for your user password, as it needs administrative privileges to install.

3. **Xcode Build Tools:** During the Homebrew installation process, it will also install the Xcode Command Line Tools if they are not already installed. These tools are essential for various developer tasks and are a prerequisite for many software packages.

4. **Verify Installation:** To confirm that Homebrew is successfully installed, open a new Terminal window and run:

    ```sh
    brew --version
    ```

   This command should display the version of Homebrew you installed.

#### Using Homebrew

Now that Homebrew is installed, you can start using it to manage software packages. Here are some common Homebrew commands:

- **Install a Package:** To install a package, use the `brew install` command followed by the package name. For example:

    ```sh
    brew install <package-name>
    ```

- **Update Homebrew:** Keep Homebrew itself up to date by running:

    ```sh
    brew update
    ```

- **Update Installed Packages:** To update all the packages you've installed with Homebrew to their latest versions, use:

    ```sh
    brew upgrade
    ```

- **Search for Packages:** If you're not sure about the exact package name, you can search for packages using:

    ```sh
    brew search <keyword>
    ```

- **View Installed Packages:** To see a list of all installed packages, use:

    ```sh
    brew list
    ```

These are just a few basic commands to get you started with Homebrew. The package manager offers a wide range of functionality and a vast library of available packages for various purposes.


####  After Homebrew is done installing, we will use it to install everything else we need.

### Terminal

The first app I install is to replace the built in `Terminal`.

The first application I install to enhance my terminal experience is [iTerm2](https://iterm2.com/). iTerm2 is my preferred terminal emulator because it offers several advantages over the built-in `Terminal` app, including:

- **Nice Window Chrome:** iTerm2 provides an aesthetically pleasing window frame and user interface elements, enhancing the overall visual experience.

- **Customization Options:** It offers extensive customization options, allowing users to tailor the terminal to their preferences, including themes, fonts, and color schemes.

- **Clickable Links:** iTerm2 recognizes clickable links within the terminal, making it easy to open URLs or navigate to file paths with a simple click.

- **Native OS Notifications:** You can receive native OS notifications for terminal events, such as command completion or important system updates.

For those not familiar with the term "window chrome," it refers to the graphical elements that make up the non-content portions of a user interface, such as window frames, buttons, and scroll bars.

To install iTerm2 using Homebrew, you can use the Homebrew "cask" feature. Casks are used to install full applications, similar to what you might download from the App Store. Run the following command in your Terminal:

```sh
brew install --cask iterm2
```

Once installed, launch it and customize the settings / preferences to your liking. These are my preferred settings:

* Appearance
  * Theme
    * Minimal
* Profiles
  * Default
      * General -> Working Directory -> Reuse previous session's directory
      * Colors -> I have a color template. I'll share it with you
      * Text -> Font -> Hack Nerd Font Mono
          * You can download this font [here](https://www.nerdfonts.com/font-downloads).
      * Text -> Font Size -> 13
      * Keys -> Key Mappings -> Presets -> Natural Text Editing
          * This allows me to use the [keyboard shortcuts](https://gist.github.com/w3cj/022081eda22081b82c52) I know and love inside of iTerm2

### Shell

Mac now comes with `zsh` as the default [shell](https://en.wikipedia.org/wiki/Comparison_of_command_shells).

#### Oh My Zsh Installation

Oh My Zsh is installed by running one of the following commands in your terminal. You can install this via the command-line with either `curl`, `wget` or another similar tool.

| Method    | Command                                                                                           |
| :-------- | :------------------------------------------------------------------------------------------------ |
| **curl**  | `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"` |
| **wget**  | `sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`   |
| **fetch** | `sh -c "$(fetch -o - https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"` |

_Note that any previous `.zshrc` will be renamed to `.zshrc.pre-oh-my-zsh`. After installation, you can move the configuration you want to preserve into the new `.zshrc`._

#### Manual inspection

It's a good idea to inspect the install script from projects you don't yet know. You can do
that by downloading the install script first, looking through it so everything looks normal,
then running it:

```sh
wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh
sh install.sh
```

#### Using Oh My Zsh

#### Plugins

Oh My Zsh comes with a shitload of plugins for you to take advantage of. You can take a look in the [plugins](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins) directory and/or the [wiki](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins) to see what's currently available.

#### Enabling Plugins

Once you spot a plugin (or several) that you'd like to use with Oh My Zsh, you'll need to enable them in the `.zshrc` file. You'll find the zshrc file in your `$HOME` directory. Open it with your favorite text editor and you'll see a spot to list all the plugins you want to load.

```sh
vi ~/.zshrc
```

For example, this might begin to look like this:

```sh
plugins=(
  git
  bundler
  dotenv
  macos
  rake
  rbenv
  ruby
)
```

_Note that the plugins are separated by whitespace (spaces, tabs, new lines...). **Do not** use commas between them or it will break._

#### Using Plugins

Each built-in plugin includes a **README**, documenting it. This README should show the aliases (if the plugin adds any) and extra goodies that are included in that particular plugin.

#### Themes

We'll admit it. Early in the Oh My Zsh world, we may have gotten a bit too theme happy. We have over one hundred and fifty themes now bundled. Most of them have [screenshots](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes) on the wiki (We are working on updating this!). Check them out!

#### Selecting a Theme

_Robby's theme is the default one. It's not the fanciest one. It's not the simplest one. It's just the right one (for him)._

Once you find a theme that you'd like to use, you will need to edit the `~/.zshrc` file. You'll see an environment variable (all caps) in there that looks like:

```sh
ZSH_THEME="robbyrussell"
```

To use a different theme, simply change the value to match the name of your desired theme. For example:

---
My favourite theme for oh my zsh is `powerlevel10k`

`Powerlevel10k` is a highly customizable Zsh theme for Oh My Zsh that provides a feature-rich and visually appealing terminal prompt. It is designed to be fast and responsive, even on large Git repositories or complex directory structures. Here are the steps to install and configure Powerlevel10k with Oh My Zsh:

#### Install Powerlevel10k Theme:
```sh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/.oh-my-zsh/themes/powerlevel10k
```

#### Configure Oh My Zsh to Use Powerlevel10k:

To set `Powerlevel10k` as your Oh My Zsh theme, edit your `~/.zshrc` configuration file. You can use a text editor to open it, for example:

```sh 
vim ~/.zshrc
````
Find the ZSH_THEME line and change it to:
```shell
ZSH_THEME="powerlevel10k/powerlevel10k"
```
#### Enable Recommended Fonts:

`Powerlevel10k` relies on specific fonts that include special symbols and icons for its appearance. You should install one of the recommended fonts to ensure everything looks as intended. A popular choice is the "Meslo Nerd Font" family, which you can install using Homebrew:

```shell
# Install Meslo Nerd Font using Homebrew
brew tap homebrew/cask-fonts
brew install --cask font-meslo-nerd-font
```

#### Restart Your Shell:

After making these changes, restart your terminal or run:

```shell
source ~/.zshrc
```

#### Configure Powerlevel10k (Optional. But I'm recommending this step):

Powerlevel10k offers an interactive configuration wizard the first time you start a new shell session with it. It helps you customize the theme to your preferences. To trigger this wizard, simply open a new terminal window or run:


```shell
p10k configure
```

Follow the prompts and customize the theme according to your preferences. You can choose between various styles, fonts, and icons.

#### Additional Customization (Optional):

You can further customize `Powerlevel10k` by editing the `~/.p10k.zsh` configuration file. This file allows you to fine-tune various aspects of the theme, such as prompt segments, colors, and layout.

That's it! You should now have `Powerlevel10k` installed and configured as your Zsh theme, providing you with a highly customizable and visually appealing terminal prompt. Enjoy your enhanced terminal experience!

---
In case you did not find a suitable theme for your needs, please have a look at the wiki for [more of them](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes).

If you're feeling feisty, you can let the computer select one randomly for you each time you open a new terminal window.

```sh
ZSH_THEME="random" # (...please let it be pie... please be some pie..)
```

And if you want to pick random theme from a list of your favorite themes:

```sh
ZSH_THEME_RANDOM_CANDIDATES=(
  "robbyrussell"
  "powerlevel10k"
)
```

If you only know which themes you don't like, you can add them similarly to an ignored list:

```sh
ZSH_THEME_RANDOM_IGNORED=(pygmalion tjkirch_mod)
```

---

#### Install the latest version of git

My Mac came with `git` version `2.32.1`, we can use brew to install the latest version of `git`:

```sh
git --version
brew install git
```

Open a new tab / window to start using the latest version:

```sh
git --version
```

Configure git with your name / email and preferred editor:

```sh
git config --global user.name dulanwirajith

git config --global user.email dulanwirajith1995@gmail.com

git config --global core.editor vim
```

#### Other command line tools I use

* [ffmpeg](https://en.wikipedia.org/wiki/FFmpeg) - edit videos from the command line
* [imagemagick](https://en.wikipedia.org/wiki/ImageMagick) - edit images from the command line

```sh
brew install ffmpeg
brew install imagemagick
```

## OS Productivity

### Window Management

I know this feature is built in to a lot of other operating systems, but it is not built in to a Mac, so we need an app for it.

I use [rectangle](https://rectangleapp.com/) to move and resize windows using keyboard shortcuts. I used to use [spectacle](https://www.spectacleapp.com/), but rectangle is more regularly maintained and allows me to use all of the same keyboard shortcuts as spectacle.

I highly recommend installing this and memorizing the keyboard shortcuts. Fluid and seamless window management is key to being productive while coding.

```sh
brew install rectangle
```

### App Switching

The built in App switcher only shows application icons, and only shows 1 icon per app regardless of how many windows you have open in that app.

I use an app switcher called [AltTab](https://alt-tab-macos.netlify.app/). It shows full window previews, and has an option to show a preview for every open window in all applications (even minimized ones).

I replace the built-in `CMD+TAB` shortcut with AltTab.

```sh
brew install alt-tab
```

### Quick Launching

The built in spotlight search is a bit slow for me and usually has web search results as the default instead of apps or folders on my machine.

I use [Alfred](https://www.alfredapp.com/) to launch apps / folders. There are features locked behind the paid powerpack.

```sh
brew install alfred
```

## Other Apps I Use Daily

* [docker](https://www.docker.com/) - Accelerate how you build, share, and run applications
* [rize](https://rize.io/) - Fully automatic time tracker that uses A.I. to improve your focus and build better work habits.
* [pgAdmin](https://www.pgadmin.org/) - The most popular and feature rich Open Source administration and development platform for PostgreSQL
* [sequel pro](https://www.sequelpro.com/) - is a fast, easy-to-use Mac database management application for working with MySQL databases 
* [firefox-developer-edition](https://www.mozilla.org/en-US/firefox/developer/) - Preferred web browser
* [app-cleaner](https://freemacsoft.net/appcleaner/) - When removing an app, will search your file system for related files / settings that should be removed as well
* android-file-transfer - Transfer files to / from my android phone
* android-platform-tools - Installs `adb` without the need for the full android studio.

[//]: # (* [keepingyouawake]&#40;https://keepingyouawake.app/&#41; - Prevents my Mac from going to sleep)

* [amphetamine](https://apps.apple.com/us/app/amphetamine/id937984704?mt=12) - Prevents my Mac from going to sleep
* [discord](https://discord.com/) - Messaging / Community
* [vlc](https://www.videolan.org/) - I use VLC to watch videos instead of the built in QuickTime.
* [kap](https://getkap.co/) - Screen recorder / gif maker
* [time-out](https://www.dejal.com/timeout/) - Break timer
* [gimp](https://www.gimp.org/) - Image editor
* [inkscape](https://inkscape.org/) - Vector editor
* [visual-studio-code](https://code.visualstudio.com/) - Code Editor
* [jetbrains toolbox](https://www.jetbrains.com/lp/toolbox/#:~:text=JetBrains-,Toolbox,range%20of%20languages%20and%20technologies) - A suite of professional development tools for a range of languages and technologies for people who using Jetbrains tools
* [intellij](https://www.jetbrains.com/products/) - Code Editor
* [postman](https://www.postman.com/) - HTTP / REST / GraphQL tester / requester

## OS Settings

These are my preferred settings for `Finder` and the `Dock`.

### Finder

* Finder -> Preferences
  * General -> Show these on the desktop -> Select None
      * I try to keep my desktop completely clean.
  * General -> New Finder windows show -> Home Folder
      * I prefer to see my home folder in each new finder window instead of recent documents
  * Advanced -> Show all filename extensions -> Yes
  * Advanced -> Show warning before changing an extension -> No
  * Advanced -> When performing a search -> Search the current folder
* View
  * Show Status Bar
  * Show Path Bar
  * Show Tab Bar

### Dock

I don't use the Dock at all. It takes up screen space, and I can use Alfred to launch apps and AltTab to switch between apps. I make the dock as small as possible and auto hide it.

* System Preferences
  * Dock & Menu Bar
      * Size -> Small as possible
      * Position on screen -> Bottom
      * Automatically hide and show the Dock -> Yes

## Menu Bar Customization

### System Stats Widgets

I like to see my network traffic, CPU temp / usage and RAM usage at a glance.

I used to use [iStat Menus](https://bjango.com/mac/istatmenus/), but a few people in my twitch chat pointed me to [stats](https://github.com/exelban/stats), a FOSS menu bar stats app. I tried it out, and I like it so far.

In each widget, a key setting to look for is under "widget settings", choose "merge widgets into one".

```sh
brew install stats
```

### Menu Bar Calendar

I like to have a calendar in the menu bar that I can quickly look at. stats does not include one, so I found [itsycal](https://www.mowglii.com/itsycal/). It seems fine for my needs.

```sh
brew install itsycal
```

itsycal shows the date, so I hide the date in the system menu bar widget:

* System Preferences
  * Dock & Menu Bar
      * Clock
          * Show Date -> Never
          * Show Day of Week -> No

## Web Browser

### Firefox

I use Firefox because it is open source and comes from the [Mozilla Foundation](https://www.mozilla.org/en-US/about/manifesto/), a non profit company that [respects my privacy](https://www.mozilla.org/en-US/firefox/privacy/).

I use the following extensions to protect my privacy while browsing the web:

* Adblocker - [uBlock Origin](https://github.com/gorhill/uBlock)
* Tracker Blocker - [Privacy Badger](https://privacybadger.org/)
  * Firefox now includes tracker blocking, but I leave Privacy Badger enabled.
* [Cookie Autodelete](https://github.com/Cookie-AutoDelete/Cookie-AutoDelete)
  * Removes cookies from websites that are not in my whitelist whenever a tab is closed. An additional precaution to tracker blocking.
* [Decentraleyes](https://decentraleyes.org/)
  * Caches CDN links locally and intercepts requests to serve from the cache. Prevents CDNs from tracking you across websites.


## Node.js

I use nvm to manage the installed versions of Node.js on my machine. This allows me to easily switch between Node.js versions depending on the project I'm working in.

See installation instructions [here](https://github.com/nvm-sh/nvm#installing-and-updating).

OR run this command (make sure v0.39.1 is still the latest)

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

After installation you'll want to add the following to your .bash_profile / .zshrc etc.

```sh
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" ## This loads nvm
```

Now that nvm is installed, you can install a specific version of node.js and use it:

```sh
nvm install 18
nvm use 18
node --version
```

## Break Timer

I use an app called [Time Out](https://www.dejal.com/timeout/).

I have it setup to show:
* 10 second micro break every 15 minutes
* 5 minute long break every 60 minutes

There is also a cross platform break timer call [Stretchly](https://hovancik.net/stretchly/). I have not used it but a lot of people have recommended it.
