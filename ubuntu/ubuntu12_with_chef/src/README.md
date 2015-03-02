# My Vagrant with Chef

Author: Lin Dong

Date: Thu Feb 19 22:56:03 PST 2015


## Quick install

Simply run this from unzipped folder `bash install.sh`

Env: Ubuntu 12.04

Chef:

* 'apt'
* 'tmux'
* 'vim'
* 'git'
* 'redis'
* 'sqlite'
* 'postgresql'
* 'nodejs'
* 'python'
* 'ruby'
* 'rbenv'
* 'zsh'
* 'oh-my-zsh', set up oh-my-zsh theme and zsh as default.

Vagrantfile is a main Vagrant configuration. Typically it is supposed to be placed at the root of your project. Just put it whenever you want your box root should be. Additional documentation can be found here.

Cheffile describes sources of cookbooks we use to provision packages you demanded. It's used by Librarian to download all the cookbooks you need including referenced dependencies. Unless you already have it install it using gem install librarian-chef command.

# Reference

1. Rove.io
2. http://vagrantbox.ex
3. http://chef.github.io/bento/
