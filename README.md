nginxがコケるので直す
nvmのinstallを追加する
```
ansible-playbook -i inventories/vagrant site.yml --private-key ~/.ssh/id_rsa -u vagrant --ask-sudo-pass

sudo useradd deploy
sudo passwd deploy
sudo visudo 
```

```
deploy ALL ALL
```
を追加
鍵を追加
```
add .ssh and authorized_keys
chmod 700 .ssh
chmod 700 .ssh/authorized_keys
```
```
mkdir www
```
```
nginxを書き換え
```
```
$ sudo -u postgres psql
create user deploy with password 'deploy';
alter role deploy createdb;
```
