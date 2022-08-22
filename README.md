[![GitHub issues](https://img.shields.io/github/issues/garutilorenzo/ansible-collection-elk)](https://github.com/garutilorenzo/ansible-collection-elk/issues)
![GitHub](https://img.shields.io/github/license/garutilorenzo/ansible-collection-elk)
[![GitHub forks](https://img.shields.io/github/forks/garutilorenzo/ansible-collection-elk)](https://github.com/garutilorenzo/ansible-collection-elk/network)
[![GitHub stars](https://img.shields.io/github/stars/garutilorenzo/ansible-collection-elk)](https://github.com/garutilorenzo/ansible-collection-elk/stargazers)


# Install and configure the ELK stack

Install and configure the ELK stack:

* [elasticsearch](https://www.elastic.co/elasticsearch/)
* [logstash](https://www.elastic.co/logstash/)
* [kibana](https://www.elastic.co/kibana/)

Elastic Beats:

* [filebeat](https://www.elastic.co/beats/filebeat)
* [metricbeat](https://www.elastic.co/beats/metricbeat)
* [heartbeath](https://www.elastic.co/beats/heartbeat)

## Requirements

Install ansible, ipaddr and netaddr:

```
pip install -r requirements.txt
```

## Roles documentation

You can refer to the README.md file in each role directory:

* [elasticsearch](roles/elasticsearch/)
* [kibana](roles/kibana/)
* [logstash](roles/logstash/)
* [beats](roles/beats/)

you can also explore all roles variables [here](docs/ROLES_VARS.md)

## Using this collection

Install from GitHub

```
ansible-galaxy collection install git+https://github.com/garutilorenzo/ansible-collection-elk
```

## Examples

[How](examples/) to use this Ansible collection

## Vagrant

To test this collection you can use [Vagrant](https://www.vagrantup.com/) and [Virtualbox](https://www.virtualbox.org/) to bring up a example infrastructure. Once you have downloaded this repo use Vagrant to start the virtual machines:

```
vagrant up
```

In the Vagrantfile you can inject your public ssh key directly in the authorized_keys of the vagrant user. You have to change the *CHANGE_ME* placeholder in the Vagrantfile. You can also adjust the number of the vm deployed by changing the NNODES variable (Default: 6)