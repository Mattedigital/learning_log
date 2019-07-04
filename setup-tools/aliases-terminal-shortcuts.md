# Aliases \(terminal shortcuts\)

A Terminal alias is a name or shortcut for one or multiple commands. Using an easy to remember alias, we can turn the above four step process into just one.

An alias can be made temporarily \(just for the use of one terminal session\) or permanently. As we want this to be a shortcut used now and in the future, let’s make it permanent:

1. Open Terminal found in Finder 

   &gt;

    Applications 

   &gt;

    Utilities

2. In Terminal, paste the following:

   `sudo nano ~/.bash_profile`

3. Enter your Mac’s administration password if required, then hit return
4. At the bottom of the open .bash\_profile file, paste the following:

   `alias showFiles='defaults write com.apple.finder AppleShowAllFiles YES; killall Finder /System/Library/CoreServices/Finder.app'`

5. Below that, paste the following:`alias hideFiles='defaults write com.apple.finder AppleShowAllFiles NO; killall Finder /System/Library/CoreServices/Finder.app'`
6. Press ctrl + O and hit return to save the file
7. Press ctrl + X to exit the file and return to the command line
8. In Terminal, paste the following: `source ~/.bash_profile` to refresh your profile and make the aliases available

![Adding aliases to .bash\_profile via Terminal](https://ianlunn.co.uk/wp-content/uploads/Screen-Shot-2014-01-06-at-15.46.22.png)

Adding aliases to .bash\_profile via Terminal

Now when you want to show hidden files, all you need type in Terminal is`showFiles`, then`hideFiles`when you want to hide them.

If you want to modify the behaviour or alias names, let’s take a closer look at the commands you just added:

```text
alias showFiles='defaults write com.apple.finder AppleShowAllFiles YES;
killall Finder /System/Library/CoreServices/Finder.app'
```

`alias`tells Terminal we’re adding a new alias.

`showFiles`is the name of the alias. Change this to what you wish.

We then give the alias two commands. The first being:

```text
defaults write com.apple.finder AppleShowAllFiles YES;
```

This is the command to show hidden files and is ended with a semi-colon`;`so we can then use the second command:

```text
killall Finder /System/Library/CoreServices/Finder.app
```

This will relaunch the Finder \(to replicate the step of holding the ‘Option/alt’ key then right clicking the Finder icon in the dock\).

