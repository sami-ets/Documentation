#Homebrew

[Homebrew](https://brew.sh) calls itself The missing package manager for macOS and is an essential tool for any developer.

##Installation

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

If everything is good, you should see no warnings, and a message that you are "ready to brew!".