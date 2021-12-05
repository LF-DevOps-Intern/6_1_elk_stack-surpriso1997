# collecting metrich beat:

Metric beat was installed as a part of assingment number A:

- After the installlation of metric beat an index template is loaded into Elastic search:

```bash
sudo metricbeat setup --template -E 'output.elasticsearch.hosts=["192.168.1.68:9200"]'

```

- An error occurred because the ports of elastic search were not allowd in the firewall:

![error](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/2/screenshots/error-connecting-to-the-elastic-server-from-metricbeat.png)

- Enabled port 9200 in firewall:

![firewall enabled](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/2/screenshots/enabled-port-9200.png)

- Merticbeat connected to elastic search server:

![metric ebat connected to server](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/2/screenshots/metricbeat-setup.png)

![metricbeat connected to kibana and elasticsearch](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/2/screenshots/metric-beat-connected-to-kibana.png)

Metrics collected in kibana:

![visializing memeory](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/2/screenshots/visualizing-system-memory.png)

![metic beat logs](https://github.com/LF-DevOps-Intern/6_1_elk_stack-surpriso1997/blob/main/2/screenshots/kiban-logs-ofmetricbeat.png)
