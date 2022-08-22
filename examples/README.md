# Examples dir

In all examples in this directory:

* firewall and selinux are disabled
* resolv mode is set to host (not DNS)

| Example | Desc |
| ------- |----------- |
| `single_elasticsearch_node`  | Single elasticsearch node with transport security and https disabled  |
| `elasticsearch_cluster`  | Elasticsearch cluster (3 master nodes, 3 data nodes)  |
| `elk_cluster`  | Elasticsearch cluster (3 master nodes, 3 data nodes), 2 kibana instances, 2 logstash instances  |
| `monitoring`  | Monitor some nodes with the elastic beats and setup the kibana dashboards  |

you can explore all roles variables [here](docs/ROLES_VARS.md)

## Generate certs

If you don't have your own CA certificate you can generate a new CA with:

```
ansible-playbook site.yml -i hosts.ini -e "generateca=yes"
```

The CA will be downloaded from the cluster in the *elasticsearch_local_certs_dir* (defaults to ~/very_secure_dir). **NOTE** create the directory on the local machine before the Ansible run.

If you already have a CA, put the CA file in the *elasticsearch_local_certs_dir* and name the certificate with *elasticsearch_ca_filename* (defaults to elastic_ca.p12)