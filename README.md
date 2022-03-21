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

## Using this collection

Install from GitHub

```
ansible-galaxy collection install git+https://github.com/garutilorenzo/ansible-collection-elk
```

## Examples

[How](examples/) to use this Ansible collection