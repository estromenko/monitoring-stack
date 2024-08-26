# infrastructure

Ansible, Docker, Prometheus, Node Exporter, Grafana, Loki, Promtail.

Dependencies:

```bash
sudo apt-get install -y openssh-server openssh-client sshpass acl ansible ansible-lint
```

WSL users might need to execute next command:

```bash
sudo mount --make-shared /
```

Sample `hosts` file:

```
[manager]
127.0.0.1 ansible_ssh_user=my_user ansible_ssh_password=secret ansible_sudo_pass=secret

[worker]
127.0.0.1 ansible_ssh_user=my_user ansible_ssh_password=secret ansible_sudo_pass=secret
```

Deploy:

```bash
ansible-playbook monitoring.yml -i hosts
```
