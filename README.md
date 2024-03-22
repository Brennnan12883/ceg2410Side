Package Installs:

Check if running as root.
Check for apt package manager.
Install required packages using apt.
Git Configuration:

Set user name, email, core editor, default exclude, and git autocorrect using git config.
Copy .gitconfig to the git repository.
Create a symbolic link to ~/.gitconfig.
Bash Run Commands (rc):

Add aliases to .bashrc.
Copy .bashrc to the git repository.
Create a symbolic link to ~/.bashrc.
SSH Public Keys - Authorized Keys:

Check if ~/.ssh folder exists. If not, create it.
Copy ~/.ssh/authorized_keys to the repository and create a symbolic link to ~/.ssh/authorized_keys.
Create ~/.ssh/config with an entry for fry.cs.wright.edu and symbolically link it to ~/.ssh/config.
Vim Customizations:

Install Vundle for managing Vim plugins.
Install a color scheme for Vim.
Install a Vim improvement plugin.
Here's a sample implementation of setup_dotfiles.sh:

bash
Copy code
#!/bin/bash

# Check if running as root
if [ "$(id -u)" -ne 0 ]; then
    echo "Please run this script as root"
    exit 1
fi

# Check for apt package manager
if ! command -v apt &> /dev/null; then
    echo "apt package manager not found"
    exit 1
fi

# Install required packages
apt install -y dnsutils nmap

# Git Configuration
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --global core.editor "vim"
git config --global core.excludesfile ~/.gitignore_global
git config --global help.autocorrect 1
cp ~/.gitconfig /path/to/dotfiles_repo/.gitconfig
ln -s /path/to/dotfiles_repo/.gitconfig ~/.gitconfig

# Bash Run Commands (rc)
echo -e "\n# Custom Aliases" >> ~/.bashrc
echo "alias ll='ls -alF'" >> ~/.bashrc
echo "alias update='sudo apt update && sudo apt upgrade -y'" >> ~/.bashrc
cp ~/.bashrc /path/to/dotfiles_repo/.bashrc
ln -s /path/to/dotfiles_repo/.bashrc ~/.bashrc

# SSH Public Keys - Authorized Keys
mkdir -p ~/.ssh
cp ~/.ssh/authorized_keys /path/to/dotfiles_repo/authorized_keys
ln -s /path/to/dotfiles_repo/authorized_keys ~/.ssh/authorized_keys
echo -e "Host fry.cs.wright.edu\n\tHostname fry.cs.wright.edu\n\tUser w_number\n\tIdentityFile ~/.ssh/id_rsa" > ~/.ssh/config
ln -s /path/to/dotfiles_repo/authorized_keys ~/.ssh/config

# Vim Customizations
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
# Pick and install color scheme using Vundle
# Pick and install Vim improvement plugin using Vundle