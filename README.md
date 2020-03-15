# Setup
This setup is for machines that are using WSL (Windows Subsystem for Linux) Ubuntu distro, zsh shell, and Oh-My-ZSH cli framework. Although any OS using an Ubuntu distro may work fine.

## Clone this repo into your $HOME directory
```bash
git clone https://github.com/eddkmm/edd-home-setup.git $HOME
```

## Install ZSH
```bash
sudo apt-get install zsh
```

## Install Oh-My-ZSH
### Via curl
```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
### Via wget
```bash
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```
If you are prompted to overwrite the .zshrc file from this repo, use this repo's .zshrc file instead. You may notice a warning about missing plugins. That's fine, we'll install them in the next step.

## Install Oh-My-ZSH plugins
Plugins will be installed in `$HOME/.oh-my-zsh-custom/plugins` which is within a custom directory we've set for ourselves. The custom directory `$ZSH_CUSTOM` was changed from `$HOME/.oh-my-zsh/custom` to `$HOME/.oh-my-zsh-custom` to ensure that we can version control changes outside the `$HOME/.oh-my-zsh` directory, which itself is its own repository.
### git-open
```bash
git clone https://github.com/paulirish/git-open.git $ZSH_CUSTOM/plugins/git-open
```
### zsh-autosuggestions
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```
### zsh-syntax-highlighting
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

## Install NVM
### Via curl
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```
### Via wget
```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```
The shell script may try to append `$NVM_DIR` variable to the end of your `.bashrc` or `.zshrc` file. Since we've already set the nvm path at the top of `.zshrc`, you can delete those appended lines if they are there.

Verify installation with `command -v nvm`. The output should be `nvm` if installation was successful.

## Install Node v10.12.0 using NVM
```bash
nvm install 10.12.0
```

## Install yarn
```bash
npm install -g yarn
```

## Install git commitizen globally
```bash
npm install -g commitizen
```

## Setup GitHub with SSH
https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh

# List of custom aliases
Command | Description
------------ | -------------
sz | Sources the `.zshrc` file. Run this every time you update this file
zrc | Opens `.zshrc` file in Vim
zalias | Opens the `.oh-my-zsh-custom/aliases.zsh` file in Vim. Edit your aliases here
gs | Alias for `git status`
y | Alias for `yarn`
ys | Alias for `yarn start`
ylinks | Lists the npm modules that are linked locally

