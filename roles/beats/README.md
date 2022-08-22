# Stup elastic Beats

Setup and configure elastic Beats

### Role variables

| Var                              | Default     | Desc |
| ------- | ------- | ----------- |
| `beats_user`                     | `elk`       | Beats system user  |
| `beats_group`                    | `elk`       | Group of the beats search system user  |
| `beats_extract_dir`              | `/opt`       | Beats extract dir   |
| `beats_version`                  | `8.1.0`       | Beats version  |
| `beats_monitoring_enabled`       | `no`       | Enable the beats http server for [monitoring purposes](https://www.elastic.co/guide/en/beats/metricbeat/current/metricbeat-module-beat.html)  |
| `filebeat_monitoring_port`       | `5066`       | filebeat http port  |
| `metricbeat_monitoring_port`     | `5067`       | metricbeat http port  |
| `heartbeat_monitoring_port`      | `5068`       | heartbeat http port  |
| `filebeat_conf_dir`              | `/etc/filebeat`       | Filebeat config directory  |
| `filebeat_certs_dir`             | `/etc/filebeat/certs`       |Filebeat certs directory  |
| `filebeat_data_dir`              | `/filebeat`       | Filebeat data directory  |
| `filebeat_log_dir`               | `/var/log/filebeat`       | Filebeat log directory  |
| `filebeat_number_of_shards`      | `1`       | Number of shard for the filebeat index template  |
| `filebeat_number_of_replicas`    | `1`       | Number of replica for the filebeat index template  |
| `metricbeat_conf_dir`            | `/etc/metricbeat`       | Metricbeat config directory  |
| `metricbeat_certs_dir`           | `/etc/metricbeat/certs`       |Metricbeat certs directory  |
| `metricbeat_data_dir`            | `/metricbeat`       | Metricbeat data directory  |
| `metricbeat_log_dir`             | `/var/log/metricbeat`       | Metricbeat log directory  |
| `metricbeat_number_of_shards`    | `1`       | Number of shard for the metricbeat index template  |
| `metricbeat_number_of_replicas`  | `1`       | Number of replica for the metricbeat index template  |
| `heartbeat_conf_dir`             | `/etc/heartbeat`       | Heartbeat config directory  |
| `heartbeat_certs_dir`            | `/etc/heartbeat/certs`       |Heartbeat certs directory  |
| `heartbeat_data_dir`             | `/heartbeat`       | Heartbeat data directory  |
| `heartbeat_log_dir`              | `/var/log/heartbeat`       | Heartbeat log directory  |
| `heartbeat_number_of_shards`     | `1`       | Number of shard for the heartbeat index template  |
| `heartbeat_number_of_replicas`   | `1`       | Number of replica for the heartbeat index template  |
| `setup_kibana_dashboards`        | `no`       | Install or not the kibana dashboards  |
| `kibana_url`                     | `''`       | kibana url required for the setup of the dashboards  |
| `elasticsearch_local_certs_dir`  | `~/very_secure_dir`       | Local directory where the Elasticsearch certificates are stored  |
| `elasticsearch_ca_name`          | `elasticsearch-ca.pem`       | Elasticsearch CA name  |
| `elasticsearch_https_enabled`    | `yes`       | Define if the Elasticsearch security [plus secured HTTPS traffic](https://www.elastic.co/guide/en/elasticsearch/reference/current/security-basic-setup-https.html) is enabled or not  |
| `elasticsearch_security_enabled`    | `yes`       | Define if [Elasticsearch security](https://www.elastic.co/guide/en/elasticsearch/reference/current/secure-cluster.html) is enabled or not |
| `elasticsearch_username`         | `kibana_system`       | Username used to connect to the elastisearch servers  |
| `elasticsearch_password`         | `K1b4nap4sSw0rd`       | password of the *elasticsearch_username*  |
| `elasticsearch_hosts`            | `[]`       | List of elasticsearch server names  |



