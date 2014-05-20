# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"
 
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
 
# use box from here: https://github.com/phusion/open-vagrant-boxes
# username: vagrant
# password: vagrant
config.vm.box = "phusion-open-ubuntu-12.04-amd64"
config.vm.box_url = "https://oss-binaries.phusionpassenger.com/vagrant/boxes/ubuntu-12.04.3-amd64-vbox.box"
 
# Provision docker on the VM
# Install Docker
pkg_cmd = "wget -q -O - https://get.docker.io/gpg | apt-key add -;" \
"echo deb http://get.docker.io/ubuntu docker main > /etc/apt/sources.list.d/docker.list;" \
"apt-get update -qq; apt-get install -q -y --force-yes lxc-docker; "
# Add vagrant user to the docker group
pkg_cmd << "usermod -a -G docker vagrant; " config.vm.provision :shell, :inline => pkg_cmd
 
