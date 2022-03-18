[![GitHub issues](https://img.shields.io/github/issues/garutilorenzo/ansible-collection-elk)](https://github.com/garutilorenzo/ansible-collection-elk/issues)
![GitHub](https://img.shields.io/github/license/garutilorenzo/ansible-collection-elk)
[![GitHub forks](https://img.shields.io/github/forks/garutilorenzo/ansible-collection-elk)](https://github.com/garutilorenzo/ansible-collection-elk/network)
[![GitHub stars](https://img.shields.io/github/stars/garutilorenzo/ansible-collection-elk)](https://github.com/garutilorenzo/ansible-collection-elk/stargazers)


# Install and configure the ELK stack

Install and configure the ELK stack:

* elasticsearch
* logstash (TODO)
* kibana

Elastic Beats:

* filebeat
* metricbeat
* heartbeath

## Requirements

Install ansible, ipaddr and netaddr:

```
pip install -r requirements.txt
```

## Roles documentation

You can refer to the README.md file in each role directory:

* [elasticsearch](roles/elasticsearch/)
* [kibana](roles/kibana/)
* [beats](roles/beats/)

## Using this collection

TBD