# Stup elasticsearch cluster

**Work in progress**

TBD

### TODO

Remove discovery.type: "single-node" from elasticsearch configuration

### How to use

Generate certs:

```
ansible-playbook site.yml -i hosts.ini -e "generateca=yes"
```

use custom certs: copy your cert under the files dir. The file **must** be named: elastic_ca.p12
