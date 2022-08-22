# Stup elasticsearch cluster

Ansible Role for elasticsearch cluster setup

**NOTE** role tested with Ansible 5.4.0

### Role variables

This role accept the following variables:

| Var   | Default | Desc |
| ------- | ------- | ----------- |
| `disable_firewall`                | `no`       | Disable firewall. Default no, if you want to configure the firewall use another Role. You can disable the firewall setting this variable to yes  |
| `disable_selinux`                | `no`       | Disable SELinux. Default no, if you want to configure SELinux use another Role. You can disable SELinux setting this variable to yes  |
| `elasticsearch_user`                | `elk`       | Elasticsearch system user  |
| `elasticsearch_group`               | `elk`       | Group of the elastic search system user  |
| `elasticsearch_extract_dir`         | `/opt`       | Elastic search extract dir  |
| `elasticsearch_data_dir`            | `/elasticsearch/data`       | Elasticsearch data dir  |
| `elasticsearch_log_dir`             | `/var/log/elasticsearch`       | Elasticsearch log dir  |
| `elasticsearch_pid_dir`             | `/var/run/elasticsearch`       | Elasticsearch pid dir |
| `elasticsearch_conf_dir`            | `/etc/elasticsearch`       | Elasticsearch conf dir  |
| `elasticsearch_certs_dir`           | `/etc/elasticsearch/certs`       | Elasticsearch certificate dir  |
| `elasticsearch_local_certs_dir`     | `~/very_secure_dir`        | Local directory where to store the Elasticsearch certificates |
| `elasticsearch_security_enabled`    | `yes`       | Enable or not the [Elasticsearch security](https://www.elastic.co/guide/en/elasticsearch/reference/current/secure-cluster.html)  |
| `elasticsearch_https_enabled`    | `yes`       | Enable or not the Elasticsearch security [plus secured HTTPS traffic](https://www.elastic.co/guide/en/elasticsearch/reference/current/security-basic-setup-https.html)  |
| `elasticsearch_ca_password`         | `c4,p4sSw0rd`       | CA password. **CHANGE** this value, is only an example password.  |
| `elasticsearch_ca_filename`         | `elastic_ca.p12`       | CA filename  |
| `elasticsearch_cert_password`       | `cerT,P4Ssw0rD`       | Certificate password. **CHANGE** this value, is only an example password.  |
| `elasticsearch_cert_filename`       | `elastic_keystore.p12`       | Certificate filename |
| `elasticsearch_http_password`       | `htTp4sS2o3d`       | HTTPS certificate password. **CHANGE** this value, is only an example password.  |
| `elasticsearch_http_file`       | `/tmp/elasticsearch-ssl-http.zip`       | Output file for the HTTPS certificate generation script |
| `elasticsearch_bootstrap_password`  | `changeme`       | Elasticsearch [bootstrap password](https://www.elastic.co/guide/en/elasticsearch/reference/current/built-in-users.html#bootstrap-elastic-passwords).  **CHANGE** this value, is only an example password. For more informatsion read [here](https://www.elastic.co/guide/en/elasticsearch/reference/current/built-in-users.html#set-built-in-user-passwords)  |
| `elasticsearch_version`             | `8.1.0`       | Elasticsearch version  |
| `elasticsearch_cluster_name`        | `elk-cluster-test`       | Elasticsearch cluster name  |
| `elasticsearch_default_node_roles`        | `list()`       | Default list of [node roles](https://www.elastic.co/guide/en/elasticsearch/reference/current/modules-node.html). If the node is a master node  all the [default roles](https://www.elastic.co/guide/en/elasticsearch/reference/current/modules-node.html#node-roles) are associeted whit the provisioned node, except the **data** role.|
| `elasticsearch_master_is_also_data_node`        | `no`       | If set to yes, the master node will be also a data node. The role **data** will be associated with the provisioned node.  |
| `elasticsearch_jvm_xmx`             | `256m`       | JVM XMX memory  |
| `elasticsearch_jvm_xms`             | `256m`       | JVM XMS memory  |
| `elasticsearch_subnet`              | `192.168.25.0/24`       | **CHANGE** this value based on your needs. This value is used to determinate the network interface to use if the machine has multiple network interfaces (Eg. Vagrant) |
| `elasticsearch_resolv_mode`         | `dns`       | How the elastic resolve the names, default dns. If set to host the /etc/hosts file will be overwritten  |
| `elasticsearch_users`         | `list()`       | List of dict. List of user with password. This role will set the default password for each user in this list. You can also use [this](https://www.elastic.co/guide/en/elasticsearch/reference/current/setup-passwords.html) tool to generate random password. To get the full list of the default password open the [main.yml](defaults/main.yml) |
| `elasticsearch_install_mode`             | `http`       | Download elasticsearch tar form elastic website. If set to local set *elasticsearch_local_tar_path*  to a local path where the tar was previously downloaded |
| `elasticsearch_local_tar_path`             | `''`       | Local path containing the elasticsearch tar  |

### Role extra variables

This role accept an extra variable *generateca*. If this value is defined the role will automatically generate the CA, example usage:

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

If you want to generate the CA, first create on the host where ansible is running the directory *elasticsearch_local_certs_dir*:

```
mkdir ~/very_secure_dir
```