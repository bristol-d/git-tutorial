# Setting up git

Choose your operating system:

  - Linux (and unix, BSD etc.): type `git` in a terminal, if you're lucky it's already installed. If not, use your package manager (this varies by flavour of linux but if you're using linux I assume you've done this before).
  - Mac: 
    - Install homebrew from [https://github.com/Homebrew/brew/releases/](https://github.com/Homebrew/brew/releases/), download the `.pkg` file of the latest version and double-click, then restart your computer.
    - In a terminal, `brew install git`.
  - Windows: download and run installer from [https://git-scm.com/download/win](https://git-scm.com/download/win). You probably want the "standalone 64-bit" version.

# Set up an account on github

  - Go to [https://github.com](https://github.com) and register.

# Create keys

You do this once per computer, not once per repository. A key is like a password for your account, only more secure.

  - Open a terminal 
    - windows: you must use the _git bash_ one from the git folder in your start menu.
    - linux/mac etc: just a normal terminal.
  - Type this then press ENTER:

```
ssh-keygen -t ed25519
```

  - Just press ENTER until it is done, you don't need a password.
  - Type the following and press ENTER after each one (note the dot on the first line):

```
cd .ssh
ls
```
  - Check that the output shows these files among others:
    - `id_ed25519` (this is your secret key and never leaves your machine)
    - `id_ed25519.pub` (this is your public key which you upload to github)
  - Type and press ENTER:

```
cat id_ed25519.pub
```
  - This prints a line of the form `ssh-ed25519 (lots of stuff)` which you select and copy to your clipboard.
    - Windows: select the whole line and just press ENTER to copy.
    - Linux: select the line, then probably CONTROL+INSERT to copy.
    - Mac OS: select the line, then use the menu EDIT / COPY.

You can now close the terminal again.

To register your key on github:

  - click your profile icon (top right of screen) then choose _Settings_.
  - Then _SSH and GPG keys_ on the left menu.
  - Click _New SSH key_.
  - Paste the public key (the `ssh-ed25519 (stuff)` line) in the key box, give it a title (this usually describes the computer it's from like "My Laptop") and press _Add SSH key_.

Your computer can now connect to github using this key. 

## If you want to back up your key

You do not need to back up the key as you can always just create a new one and register it again in the github web interface, but if you want to:

  - windows: open the git terminal, then type these commands to open a folder window:
```
cd .ssh
start .
```
  - mac/linux: the keys are in a folder `.ssh` underneath your home folder. You might have to enable "show hidden files" or a similar-named option in your file manager program to see this folder.
