# Stup logstash

Setup and configure logstash

### Role variables

| Var   | Default | Desc |
| ------- | ------- | ----------- |
| `logstash_group`               | `elk`       | Logstash system user  |
| `logstash_user`                | `elk`       | Group of the Logstash search system user  |
| `logstash_extract_dir`         | `/opt`       | Logstash search extract dir   |
| `logstash_version`             | `8.1.0`       | Logstash version  |
| `logstash_conf_dir`            | `/etc/logstash`       | Logstash data dir  |
| `logstash_log_dir`             | `/var/log/logstash`       | Logstash data dir  |
| `logstash_certs_dir`           | `/etc/logstash/certs`       | Logstash data dir  |
| `logstash_pid_dir`             | `/var/run/logstash`       | Logstash data dir  |
| `logstash_data_dir`            | `/logstash`       | Logstash data dir  |
| `logstash_beats_tcp_port`      | `5044`       | logstash beats tcp listen port  |
| `logstash_tcp_port`            | `5000`       | logstash  tcp listen port  |
| `logstash_install_mode`        | `local`       | Download Logstash tar form elastic website. If set to local set *logstash_local_tar_path*  to a local path where the tar was previously downloaded  |
| `logstash_local_tar_path`          | `''`       | Local path Logstash the elasticsearch tar  |
| `elasticsearch_local_certs_dir`  | `~/very_secure_dir`       | Local directory where the Elasticsearch certificates are stored  |
| `elasticsearch_ca_name`          | `elasticsearch-ca.pem`       | Elasticsearch CA name  |
| `elasticsearch_https_enabled`    | `yes`       | Define if the Elasticsearch security [plus secured HTTPS traffic](https://www.elastic.co/guide/en/elasticsearch/reference/current/security-basic-setup-https.html) is enabled or not  |
| `elasticsearch_security_enabled`    | `yes`       | Define if [Elasticsearch security](https://www.elastic.co/guide/en/elasticsearch/reference/current/secure-cluster.html) is enabled or not |
| `elasticsearch_username`         | `logstash_system`       | Username used to connect to the elastisearch servers  |
| `elasticsearch_password`         | `l0gst4sHpAssw0rd,`       | password of the *elasticsearch_username*  |
| `elasticsearch_hosts`            | `[]`       | List of elasticsearch server names  |
