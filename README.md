nginxがコケるので直す
ansible-playbook -i inventories/vagrant site.yml --private-key ~/.ssh/id_rsa -u vagrant --ask-sudo-pass

