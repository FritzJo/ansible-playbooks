# Ansible playbooks
This repository contains some of my Ansible playbooks that I use to manage my selfhosted services.

I am currently in the process of converting all my deployments to Ansible scripts, which means that these playbooks are mostly WIP. Everything is designed for Debian 10 targets.

## Content
* Docker
* Grafana
* Telegraf
* Nebula VPN

## Examples
### Example inventory
```bash
all:
   hosts:
     server_1:
       ansible_host: <TARGET_IP>
   children:
     server_list:
       hosts:
         server_1
       vars:
         ansible_ssh_private_key_file: 
         influx_user: 
         influx_password: 
         influx_database: 
         influx_grafana_password: 
         grafana_password: 
         telegraf_destination: 
         telegraf_database: 
```

### Deploy a Grafana + InfluxDB server
```bash
ansible-playbook logging/server/playbook_grafana.yaml -i inventory.yaml
```
