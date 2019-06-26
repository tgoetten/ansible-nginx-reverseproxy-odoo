## Install Ansible dependencies
ansible-galaxy install -r requirements.yml

## Create remote user and copy SSH keys
ansible-playbook --inventory-file=hosts.cfg setup.yml -l development --ask-pass
ansible-playbook --inventory-file=hosts.cfg setup.yml -l production --ask-pass

## Install and configure NGINX
ansible-playbook --inventory-file=hosts.cfg nginx-reverseproxy-playbook.yml -l development
ansible-playbook --inventory-file=hosts.cfg nginx-reverseproxy-playbook.yml -l production


## Open issues
- Hetzner mirror
- certbot
