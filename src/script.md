# Scripts for Ubuntu

## Vim
```bash
sudo apt-get install vim-nox
git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim
sudo apt-get install exuberant-ctags
cd .vim/bundle/vimproc.vim && make
```

## fasd
```bash
git clone http://github.com/clvv/fasd.git && cd fasd && sudo make install
```

## Color
```bash
wget --no-check-certificate https://raw.github.com/seebi/dircolors-solarized/master/dircolors.ansi-dark && mv dircolors.ansi-dark .dircolors
```

## Percol
```
sudo apt-get install python-setuptools
sudo easy_install pip
sudo pip install percol
```

## Node

```bash
curl -o node.tar.gz  http://nodejs.org/dist/v0.12.0/node-v0.12.0-linux-x64.tar.gz
cd /usr/local && sudo tar --strip-components 1 -zxf ~/node.tar.gz
```

# Reference

[More](https://gist.github.com/72d8255ce2d90e568571)
[Ubuntu dircolors](http://www.webupd8.org/2011/04/solarized-must-have-color-paletter-for.html)
