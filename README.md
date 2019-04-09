## VMware tool

sudo apt-get autoremove open-vm-tools

sudo apt-get install open-vm-tools-desktop

## Install tools

```sh
sudo apt-get install xsel meld minicom git zsh build-essential cmake clang exuberant-ctags cscope silversearcher-ag python-pip python3-pip python-dev tig tmux-next speedcrunch htop
```
## Install i386 support

```sh
sudo dpkg --add-architecture i386
sudo apt install libc6:i386
```

## Oh My Zsh
[Follow instruction here](https://github.com/robbyrussell/oh-my-zsh)

```sh
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

Use theme agnoster.

Use plugin z extract thefuck

Add config for thefuck

```sh
eval "$(thefuck --alias)"
```

Install thefuck

```sh
sudo pip3 install thefuck
```

Install fzf

```sh
git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install
```

## sublime text3

Install the GPG key:
```sh
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```
Ensure apt is set up to work with https sources:
```sh
sudo apt-get install apt-transport-https
```
Select the channel to use:

Stable
```sh
    echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```
Dev
```sh
    echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```
Update apt sources and install Sublime Text
```sh
sudo apt-get update
sudo apt-get install sublime-text
```

## Install powerline fonts

```sh
# clone
git clone https://github.com/powerline/fonts.git
# install
cd fonts
./install.sh
# clean-up a bit
cd ..
rm -rf fonts
```

Use dejavu powerline font in term.

## Build vim from source

Add x11 lib first: libx11-dev libxtst-dev

[Follow instruction here](https://github.com/Valloric/YouCompleteMe/wiki/Building-Vim-from-source)

```sh
sudo apt-get install libncurses5-dev libgnome2-dev libgnomeui-dev \
    libgtk2.0-dev libatk1.0-dev libbonoboui2-dev \
    libcairo2-dev libx11-dev libxpm-dev libxt-dev python-dev \
    python3-dev ruby-dev lua5.1 liblua5.1-dev libperl-dev git libx11-dev libxtst-dev
```

```sh
sudo apt-get remove vim-tiny vim-common
```

```sh
cd ~
git clone https://github.com/vim/vim.git
cd vim
./configure --with-features=huge \
            --enable-multibyte \
            --enable-rubyinterp=yes \
            --enable-python3interp=yes \
            --with-python3-config-dir=/usr/lib/python3.4/config-3.4m-x86_64-linux-gnu \
            --enable-perlinterp=yes \
            --enable-luainterp=yes \
            --enable-gui=gtk2 --enable-cscope --prefix=/usr
make VIMRUNTIMEDIR=/usr/share/vim/vim80
```

```sh
sudo apt-get install checkinstall
cd ~/vim
sudo checkinstall
```

```
sudo update-alternatives --install /usr/bin/editor editor /usr/bin/vim 1
sudo update-alternatives --set editor /usr/bin/vim
sudo update-alternatives --install /usr/bin/vi vi /usr/bin/vim 1
sudo update-alternatives --set vi /usr/bin/vim
```

## Clone vim config

```sh
git clone git@github.com:zhangrx509/vim_config.git
cd vim_config
ln .vimrc ~/.vimrc
```

Install vundle

```sh
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

Launch vim and install plugin.

Build YCM.

```sh
cd ~/.vim/bundle/YouCompleteMe
./install.py --clang-completer
```

Change ```caps lock``` to ```ctrl``` and ```shift + caps lock``` to ```caps lock``` by editing ~/.Xmodmap

```sh
clear lock
clear control
add control = Caps_Lock Control_L Control_R
keycode 66 = Control_L Caps_Lock NoSymbol NoSymbol
```

Then execute
```sh
xmodmap ~/.Xmodmap
```

## Clone git config

```sh
git clone git@github.com:zhangrx509/git_config.git
cd git_config
cp .gitconfig ~/
cp .gitglobalignore ~/
```
# vscode tk
34c4df1b381228efb9d90ea9663ffa022038bcb8
