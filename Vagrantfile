# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|

  config.vm.box = "dubbs/centos-6.6"

  $script = <<-SCRIPT

  # http://fgimian.github.io/blog/2014/04/20/better-python-version-and-environment-management-with-pyenv/

  rpm -qa|grep openssl-devel > /dev/null
  if [ $? -ne 0 ];then
    rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm
    yum -y install git gcc zlib-devel bzip2-devel readline-devel sqlite-devel openssl-devel
  fi

  if [ ! -d "$HOME/.pyenv" ]; then
    curl -L https://raw.github.com/yyuu/pyenv-installer/master/bin/pyenv-installer | bash
    printf 'export PATH="$HOME/.pyenv/bin:$PATH"\n' >> $HOME/.bash_profile
    printf 'eval "$(pyenv init -)"\n'               >> $HOME/.bash_profile
    printf 'eval "$(pyenv virtualenv-init -)"\n'    >> $HOME/.bash_profile
  fi

  pyenv versions|grep 2.7 > /dev/null
  if [ $? -ne 0 ];then
    pyenv install 2.7.10
    printf 'pyenv global 2.7.10' >> $HOME/.bash_profile
  fi

  if [ ! -f /vagrant/.python-version ];then
    cd /vagrant
    pyenv virtualenv blog
    pyenv local blog
    pip install pelican markdown
  fi

  #cd /vagrant
  #pelican-quickstart

  SCRIPT

  config.vm.provision "shell", inline: $script

end
