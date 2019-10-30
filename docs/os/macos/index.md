# System Preferences

Various system configuration and reminders for using macOS as a development machine.


## First Time Setup

The first thing to do is update the macOS operating system. To do that go: Apple menu () > About This Mac > Software Update.

If this is a new computer there are a couple tweaks you could make to the System Preferences. These settings are all optional, consider them suggestions. Always choose the setting that suits you the best..


### Users & Groups

- Disable Guest User.
- Set up Password, Apple ID, Picture, etc.


### Trackpad

Enable all desired options, such as `Secondary click`.


### Dock

Turn on `Magnification` by checking the box. Adjust Dock size as desired.


### Bluetooth

Check `Show Bluetooth in menu bar`.


### Sound

Check `Show volume in menu bar`.


### Finder

Click *Finder* in the Menu bar at the top -> Preferences.
 
- General
    - Show External Disks, CDs, DVDs, and iPods, Connected servers.
    - Change New finder window show to open in your Home Directory
- Sidebar
    - Check all desired items in the sidebar.
 
 
### Menu bar

- Battery
    - Click on the battery -> Show percentage.
- Clock
    - Click on Clock -> Open Date & Time Preferences...
    - Check Display the time with seconds
    - Check Use a 24-hour clock
    - Date options : Check Show the day of the week and Show date.


### Accounts

Add an iCloud account and sync Calendar, Find my Mac, Contacts etc.


# Xcode

[Xcode](https://developer.apple.com/xcode/) is an integrated development environment for macOS containing a suite of
software development tools developed by Apple for developing software for macOS, iOS, watchOS and tvOS.

Download and install it from the [App Store](https://apps.apple.com/ca/app/xcode/id497799835?mt=12).

For Git tools, you will need to install Xcode command line tools.

After downloading and installing Xcode from the App Store, install the Xcode command line tools. Run:

```
$ xcode-select --install
```

It'll prompt you to install the command line tools. Follow the instructions and you'll have Xcode and Xcode command line
tools both installed.


# XQuartz

XQuartz is Apple Inc.'s version of the X server, a component of the X Window System for macOS. It might be useful to run
X Window applications remotely from servers. Download and install from [XQuartz](http://xquartz.macosforge.org/landing/).

# Sourcetree

[Sourcetree app](https://www.sourcetreeapp.com) is an Atlassian Git GUI tool to interact visually with your Git repositories.

It's the best tool for managing Git repositories, have a look on what you do and changed in you code, and is fully-featured. You can download it for free [here](https://www.sourcetreeapp.com)

# Git

To test that Git is installed properly, run:

```
$ git --version
```

And which git should output `/usr/local/bin/git`.

Next, we'll define your Git user (should be the same name and email you use for GitHub):

```
$ git config --global user.name "John Doe
$ git config --global user.email "john.doe@apple.com"
```

Your credentials will be added to your `.gitconfig` file.

To push code to your GitHub repositories, we're going to use the recommended HTTPS method (versus SSH). To prevent `git` from asking for your username and password every time you push a commit you can cache your credentials by running the following command, as described in the [instructions](https://help.github.com/en/github/using-git/caching-your-github-password-in-git).
Also, if you are using Two-Factor Authorization in GitHub, you must specify a Personal access tokens. To do so, go to your GitHub Profile page -> Settings -> Developer settings -> Personal access tokens.
Generate a new token, and paste it into Sourcetree initial's configuration when linking your Github account.


# SSH Config for GitHub

The instructions below are referenced from the official [documentation](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh).


## Check for existing SSH keys

First, we need to check for existing SSH keys on your computer. We do this by running:

```
$ ls -al ~/.ssh
# Lists the files in your .ssh directory, if they exist
```

Check the directory listing to see if you have files named either id_rsa.pub or id_dsa.pub. If you don't have either of those files then read on, otherwise skip the next section.


## Generate a new SSH key

If you don't have an SSH key you need to generate one. To do that you need to run the commands below, and make sure to substitute the placeholder with your email. The default settings are preferred, so when you're asked to "enter a file in which to save the key,"" just press Enter to continue.

```
$ ssh-keygen -t rsa -C "john.doe@apple.com"
# Creates a new ssh key, using the provided email as a label
```


## Add your SSH key to the ssh-agent

Run the following commands to add your SSH key to the ssh-agent.

```
$ eval "$(ssh-agent -s)"
```

You will need to modify your `~/.ssh/config` file to automatically load keys into the ssh-agent and store passphrases in your keychain:

Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
  
Run this command to complete this step:

```
$ ssh-add -K ~/.ssh/id_rsa
```


## Adding a new SSH key to your GitHub account

The last step is to let GitHub know about your SSH key. Run this command to copy your key to your clipboard:

```
$ pbcopy < ~/.ssh/id_rsa.pub
```

Then go to GitHub and [input your new SSH key](https://github.com/settings/ssh/new). Paste your key in the "Key" textbox and pick a name that represents the computer you're currently using.


# Homebrew

[Homebrew](https://brew.sh) calls itself "The missing package manager for macOS" and is an essential tool for any 
developer.


## Installation

Before you can run Homebrew you need to have the Command Line Tools for Xcode installed. It include compilers and other tools that will allow you to build things from source, and if you are missing this it's available through the App Store > Updates. You can also install it from the terminal by running the following:

```
$ sudo xcode-select --install
```

To install Homebrew run the following in a terminal, hit Enter, and follow the steps on the screen:

```
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Then, to be able to use brew you need to start a new terminal session. After that you should make sure everything is working by running:

```
$ brew doctor
```

If everything is good, you should see no warnings, and a message that you are "Ready to brew!".


# Terminal tools

## Bash Completion

Bash completion is a bash function that allows you to auto complete commands or arguments by typing partially commands or arguments, then pressing the [Tab] key. This will help you when writing the bash command in terminal.

### Installation

```
$ brew install bash-completion
```

Bash completion will be installed in `/usr/local/etc/bash_completion.d`.

For it to work, add this to your `~/.zshrc`:

```
[ -f /usr/local/etc/bash_completion ] && . /usr/local/etc/bash_completion
```

Or simply type:

```
$ echo "[ -f /usr/local/etc/bash_completion ] && . /usr/local/etc/bash_completion" >> ~/.zshrc
```

Restart your zsh session:

```
$ source ~/.zshrc
```

### Usage

Once you've done this, you can use bash completion by pressing the tab key twice after a command. For example:

```
$ git [tab] [tab]
add            blame          cherry-pick    config         format-patch   gui            merge          push           repack         rm             stage          whatchanged
am             branch         citool         describe       fsck           help           mergetool      range-diff     replace        send-email     stash          worktree
apply          bundle         clean          diff           gc             init           mv             rebase         request-pull   shortlog       status
archive        checkout       clone          difftool       gitk           instaweb       notes          reflog         reset          show           submodule
bisect         cherry         commit         fetch          grep           log            pull           remote         revert         show-branch    tag
More
```

You can list additional completion packages are available by typing:

```
$ brew search completion
```

And you can install them using brew install commands, for example:

```
$ brew install docker-completion
```

You can also manually add a bash completion file into `/usr/local/etc/bash_completion.d`


## Other terminal apps

Several other terminal apps exist for macOS. Among these, [hyper](http://hyper.is) and [iTerm2]() are very popular.
You might want to have a look on these. 