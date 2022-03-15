# Stup elasticsearch cluster

Ansible Role for elasticsearch cluster setup

### Requirements

Install ansible, ipaddr and netaddr:

```
pip install -r requirements.txt
```

**NOTE** role tested with Ansible 5.4.0

### Role variables

This role accept the following variables:

| Var   | Default | Desc |
| ------- | ------- | ----------- |
| `elasticsearch_user`                | `elk`       | Elasticsearch system user  |
| `elasticsearch_group`               | `elk`       | Group of the elastic search system user  |
| `elasticsearch_extract_dir`         | `/opt`       | Elastic search extract dir  |
| `elasticsearch_data_dir`            | `/elasticsearch/data`       | Elasticsearch data dir  |
| `elasticsearch_log_dir`             | `/var/log/elasticsearch`       | Elasticsearch log dir  |
| `elasticsearch_pid_dir`             | `/var/run/elasticsearch`       | Elasticsearch pid dir |
| `elasticsearch_conf_dir`            | `/etc/elasticsearch`       | Elasticsearch conf dir  |
| `elasticsearch_certs_dir`           | `/etc/elasticsearch/certs`       | Elasticsearch certificate dir  |
| `elasticsearch_security_enabled`    | `yes`       | Enable or not the [Elasticsearch security](https://www.elastic.co/guide/en/elasticsearch/reference/current/secure-cluster.html)  |
| `elasticsearch_ca_password`         | `c4,p4sSw0rd`       | CA password. **CHANGE** this value, is only an example password.  |
| `elasticsearch_ca_filename`         | `elastic_ca.p12`       | CA filename  |
| `elasticsearch_cert_password`       | `cerT,P4Ssw0rD`       | Certificate password. **CHANGE** this value, is only an example password.  |
| `elasticsearch_cert_filename`       | `elastic_keystore.p12`       | Certificate filename |
| `elasticsearch_bootstrap_password`  | `changeme`       | Elasticsearch [bootstrap password](https://www.elastic.co/guide/en/elasticsearch/reference/current/built-in-users.html#bootstrap-elastic-passwords).  **CHANGE** this value, follow [this](https://www.elastic.co/guide/en/elasticsearch/reference/current/built-in-users.html#set-built-in-user-passwords) instructions  |
| `elasticsearch_env_file`            | `dict`       | Yaml dict, see defaults.yaml. Specify env path based on the Linux distribution  |
| `elasticsearch_version`             | `8.1.0`       | Elasticsearch version  |
| `elasticsearch_cluster_name`        | `elk-cluster-test`       | Elasticsearch cluster name  |
| `elasticsearch_jvm_xmx`             | `256m`       | JVM XMX memory  |
| `elasticsearch_jvm_xms`             | `256m`       | JVM XMS memory  |
| `elasticsearch_subnet`              | `192.168.25.0/24`       | **CHANGE** this value based on your needs. This value is used to determinate the network interface to use if the machine has multiple network interfaces (Eg. Vagrant) |
| `elasticsearch_resolv_mode`         | `dns`       | How the elastic resolve the names, default dns. If set to host the /etc/hosts file will be overwritten  |

### Role extra variables

This role accept an extra variables *generateca*. If this value is defined the role will automatically generate the CA, example usage:

```
ansible-playbook site.yml -i hosts.ini -e "generateca=yes"
```

### Inventory

We need to define our inventory with at least two groups:

* elasticsearch_master: group of the elasticsearch master nodes
* elasticsearch_ca: node where the CA will be generated (**NOTE** only one node must be set in this group)

An example inventory would be:

```
[elasticsearch_master]
elk-node1 ansible_host=192.168.X.X
elk-node2 ansible_host=192.168.X.X

[elasticsearch_ca]
elk-node1 ansible_host=192.168.X.X

[elasticsearch:children]
elasticsearch_master
```

### How to use this role


```
ansible-playbook site.yml -i hosts.ini
```

example site.yml

```yaml
---
- hosts: all
  become: yes
  remote_user: "remote_user"
  roles: 
    - role: ansible-role-linux-elasticsearch
  vars_files:
    - vars.yml
```