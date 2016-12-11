nginxがコケるので直す
nvmのinstallを追加する
ansible-playbook -i inventories/vagrant site.yml --private-key ~/.ssh/id_rsa -u vagrant --ask-sudo-pass

