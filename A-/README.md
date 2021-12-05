# Installing and configuring elastic search and metricbeat:

These are the steps followed:

1. Insalling elastic search:

- Adding elastic search keys

```bash
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -

```

![image](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/A-/screenshot/elastic-and-kibana/add-elastic-search-gpg-keys.png)

- Insatalling elasticserach package after updating the apt:

```bash
sudo apt-get update
sudo apt install elasticsearch

```

![iamge](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/A-/screenshot/elastic-and-kibana/installing-elastic-search.png)

- Editing the elastic search conf file located at `/etc/elasticsearch/elacsearch.yml` with `vi` adding the network related configuration:

```bash

network.host:192.168.1.68
discovery.type: single-node
xpack.security.enabled: true
xpack.security.authc.api_key.enabled: true

```

Also set the discovery.type to `sigle-node`

![image](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/A-/screenshot/elastic-and-kibana/added-configs-enabled-single-node.png)

> where, network.host= host's ip address

- Checking elasticsearch's service status which is disabled by default:

```bash
sudo systemctl status elasticsearch
```

![iamge](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/A-/screenshot/elastic-and-kibana/by-default-disabled.png)

- Enable elasticsearch service:

```bash
sudo systemctl status enable elasticsearch
sodo systemctl start elasticsearch
```

- Setting up password for the ELK stack:
  To run the script to set password, the current dir was changed to `/usr/share/elasticsearch/bin`:

![cd to binaries](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/A-/screenshot/elastic-and-kibana/cd-to-usr-share-elasticsearch.png)

- Passwords were set running the `elasticsearch-setup-passwords` script :

```bash
sudo ./elasticsearch-setup-passwords interactive


```

![setting up password](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/A-/screenshot/elastic-and-kibana/set-password-to-all-the-systems.png)

After that elasticsearch was up and running:

![image](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/A-/screenshot/elastic-and-kibana/elastic-search-running.png)

- Elastic search running in browser:
  ![image](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/A-/screenshot/elastic-and-kibana/elastic-search-running-browser.png)

- Elastic search running and asking for username and password:

![asking for password](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/A-/screenshot/elastic-and-kibana/elastic-serach-asking-for-password.png)
