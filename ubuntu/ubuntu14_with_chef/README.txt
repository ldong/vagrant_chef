How to use
Quick install

Simply run this from unzipped folder `bash install.sh`

Manually

The ZIP file you are downloading contains two files: Vagrantfile and Cheffile.

Vagrantfile is a main Vagrant configuration. Typically it is supposed to be placed at the root of your project. Just put it whenever you want your box root should be. Additional documentation can be found here.
Cheffile describes sources of cookbooks we use to provision packages you demanded. It's used by Librarian to download all the cookbooks you need including referenced dependencies. Unless you already have it install it using gem install librarian-chef command.
To finalize the setup and run your box you should:

put both of files to the root of your project (it will be the root of a virtual box)
run librarian-chef install to grab required cookbooks
run vagrant up to download, provision and start your brand new box environment.

# Reference
1. Rove.io
2. http://vagrantbox.ex
3. http://chef.github.io/bento/
