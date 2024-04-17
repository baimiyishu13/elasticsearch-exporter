# Elasticsearch Exporter Ansible 角色

这个 Ansible 角色用于二进制方式安装和配置 Elasticsearch Exporter。

## 需求

- 在线安装

## 角色变量

| 变量                                  |                                                              |
| ------------------------------------- | ------------------------------------------------------------ |
| elasticsearch_exporter_version        | 1.5.0                                                        |
| elasticsearch_exporter_download_url   | https://github.com/prometheus-community/elasticsearch_exporter/releases/download/v{{ elasticsearch_exporter_version }}/elasticsearch_exporter-{{ elasticsearch_exporter_version }}.linux-amd64.tar.gz |
| elasticsearch_exporter_install_dir    | /usr/local/bin                                               |
| elasticsearch_node_ip                 | 10.61.200.236                                                |
| elasticsearch_node_port               | 9200                                                         |
| elasticsearch_exporter_listen_address | 0.0.0.0:9114                                                 |

## 依赖项

暂时没有依赖项。

## 示例 Playbook

```yaml
---
- hosts: el
  become: yes
  become_method: sudo
  roles:
    - role: elasticsearch-exporter
      vars:
        elasticsearch_node_ip: "10.61.200.236"