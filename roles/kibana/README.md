# Stup kibana

Setup and configure Kibana

### Role variables

| Var   | Default | Desc |
| ------- | ------- | ----------- |
| `kibana_user`                | `elk`       | Kibana system user  |
| `kibana_group`               | `elk`       | Group of the kibana search system user  |
| `kibana_extract_dir`         | `/opt`       | Kibana search extract dir   |
| `kibana_version`             | `8.1.0`       | Kibana version  |
| `kibana_conf_dir`            | `/etc/kibana`       | Kibana data dir  |
| `kibana_log_dir`             | `/var/log/kibana`       | Kibana data dir  |
| `kibana_certs_dir`           | `/etc/kibana/certs`       | Kibana data dir  |
| `kibana_pid_dir`             | `/var/run/kibana`       | Kibana data dir  |
| `kibana_data_dir`            | `/kibana`       | Kibana data dir  |
| `kibana_https_enabled`       | `no`       | Enable or not https for kibana  |
| `kibana_install_mode`        | `local`       | Download kibana tar form elastic website. If set to local set *kibana_local_tar_path*  to a local path where the tar was previously downloaded  |
| `kibana_local_tar_path`          | `''`       | Local path kibana the elasticsearch tar  |
| `elasticsearch_local_certs_dir`  | `~/very_secure_dir`       | Local directory where the Elasticsearch certificates are stored  |
| `elasticsearch_ca_name`          | `elasticsearch-ca.pem`       | Elasticsearch CA name  |
| `elasticsearch_https_enabled`    | `yes`       | Define if the Elasticsearch security [plus secured HTTPS traffic](https://www.elastic.co/guide/en/elasticsearch/reference/current/security-basic-setup-https.html) is enabled or not  |
| `elasticsearch_security_enabled`    | `yes`       | Define if [Elasticsearch security](https://www.elastic.co/guide/en/elasticsearch/reference/current/secure-cluster.html) is enabled or not |
| `elasticsearch_username`         | `kibana_system`       | Username used to connect to the elastisearch servers  |
| `elasticsearch_password`         | `K1b4nap4sSw0rd`       | password of the *elasticsearch_username*  |
| `elasticsearch_hosts`            | `[]`       | List of elasticsearch server names  |
