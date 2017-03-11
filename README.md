# vagrant-elk
Virtual machine for ELK stack

## BOX
This vagrant uses ubuntu/xenial64 box, the first step is to install python2.
See SHELL provisioning under Vagrantfile.

## provisioning
### SHELL
In order to execute ansible, the first step is to install python2 library.

    apt-get install -y python-minimal

The next one is unzip. But this is deprecated, for this Vagrant.

    apt-get -y install unzip

### Ansible
The next provisioning uses ansible playbook.
The playbook is located under `provisioning` folder.
The steps are:
* install JDK 8
* install elasticsearch 5.x
* install kibana
* install nginx, for kibana reverse proxy
* install logstash
* install filebeat

*Note: the ssl configuration for filebeat is disabled because this is only for demo purpose*

### Reference
https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-logstash-and-kibana-elk-stack-on-ubuntu-16-04
