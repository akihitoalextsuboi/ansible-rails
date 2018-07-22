postgresqlのバージョンが9なので10にしたい
```
rubyのversionチェック
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
ssh-keygen -t rsa
add .ssh and authorized_keys
chmod 700 .ssh
chmod 700 .ssh/authorized_keys
```
```
mkdir www
sudo chown deploy:deploy www
```
```
$ sudo -u postgres psql
create user deploy with password 'deploy';
alter role deploy createdb;
you might be needed to drop template
```
鍵をgithubに追加
```
install dotenv in rails
add .env file
add .env settings about DATABASE and secret_key_base
```
