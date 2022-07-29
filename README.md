# stax
Guide to Install Openstack Environment
sudo  apt install vim net-tools -y

sudo useradd -s /bin/bash -d /opt/stack -m stack




echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack


sudo su - stack

git clone https://opendev.org/openstack/devstack
cd devstack
vim local.conf


stack@stack:~/devstack$ cat local.conf
[[local|localrc]]
ADMIN_PASSWORD=redhat
DATABASE_PASSWORD=redhat
RABBIT_PASSWORD=redhat
SERVICE_PASSWORD=redhat

##Enable heat services
enable_service h-eng h-api h-api-cfn h-api-cw

##Enable heat plugin
enable_plugin heat https://opendev.org/openstack/heat

##Enable Heat Dashboard
enable_plugin heat-dashboard https://opendev.org/openstack/heat-dashboard




./stack.sh

![image](https://user-images.githubusercontent.com/103080332/181668527-1962a2ae-859c-4f4f-a598-b8a234de7ec8.png)
