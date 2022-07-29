# stax
Guide to Install Openstack Environment
`sudo  apt install vim net-tools -y`<br/>

`sudo useradd -s /bin/bash -d /opt/stack -m stack`<br/>




`echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack`<br/>


`sudo su - stack`<br/>

`git clone https://opendev.org/openstack/devstack`<br/>
`cd devstack`<br/>
`vim local.conf`<br/>


`stack@stack:~/devstack$ cat local.conf
[[local|localrc]]<br/>
ADMIN_PASSWORD=redhat<br/>
DATABASE_PASSWORD=redhat<br/>
RABBIT_PASSWORD=redhat<br/>
SERVICE_PASSWORD=redhat`<br/>

##Enable heat services<br/>
`enable_service h-eng h-api h-api-cfn h-api-cw`

##Enable heat plugin<br/>
`enable_plugin heat https://opendev.org/openstack/heat`

##Enable Heat Dashboard<br/>
`enable_plugin heat-dashboard https://opendev.org/openstack/heat-dashboard`




./stack.sh

![image](https://user-images.githubusercontent.com/103080332/181668527-1962a2ae-859c-4f4f-a598-b8a234de7ec8.png)
