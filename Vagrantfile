# encoding: utf-8
# This file originally created at http://rove.io/8376b3aed0fa12746c0460f1f4d602af

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "opscode-ubuntu-12.04_chef-11.4.0"
  config.vm.box_url = "https://opscode-vm-bento.s3.amazonaws.com/vagrant/opscode_ubuntu-12.04_chef-11.4.0.box"
  config.ssh.forward_agent = true

  config.vm.network :forwarded_port, guest: 3000, host: 3000

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["cookbooks"]
    chef.add_recipe :apt
    chef.add_recipe 'tmux'
    chef.add_recipe 'postgresql::server'
    chef.add_recipe 'vim'
    chef.add_recipe 'sqlite'
    chef.add_recipe 'nodejs'
    chef.add_recipe 'ruby_build'
    chef.add_recipe 'rbenv::user'
    chef.add_recipe 'redis'
    chef.add_recipe 'python'
    chef.add_recipe 'git'
    chef.json = {
      :postgresql => {
        :config   => {
          :listen_addresses => "*",
          :port             => "5432"
        },
        :pg_hba   => [
          {
            :type   => "local",
            :db     => "postgres",
            :user   => "postgres",
            :addr   => nil,
            :method => "trust"
          },
          {
            :type   => "host",
            :db     => "all",
            :user   => "all",
            :addr   => "0.0.0.0/0",
            :method => "md5"
          },
          {
            :type   => "host",
            :db     => "all",
            :user   => "all",
            :addr   => "::1/0",
            :method => "md5"
          }
        ],
        :password => {
          :postgres => "password"
        }
      },
      :rbenv      => {
        :user_installs => [
          {
            :user   => "vagrant",
            :rubies => [
              "1.9.3-p484",
              "2.0.0-p353"
            ],
            :global => "2.0.0-p353"
          }
        ]
      },
      :redis      => {
        :bind        => "127.0.0.1",
        :port        => "6379",
        :config_path => "/etc/redis/redis.conf",
        :daemonize   => "yes",
        :timeout     => "300",
        :loglevel    => "notice"
      },
      :git        => {
        :prefix => "/usr/local"
      },
      :oh_my_zsh => {
        :users => [{
          :login => 'vagrant',
          :theme => 'robbyrussell',
          :plugins => %w{git rails ruby rvm virtualenv vagrant}
        }]
      }
    }
  end
end
