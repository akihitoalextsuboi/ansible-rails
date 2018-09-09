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
UPDATE pg_database SET datistemplate = FALSE WHERE datname = 'template1';
DROP DATABASE template1;
CREATE DATABASE template1 WITH TEMPLATE = template0 ENCODING = 'UNICODE';
UPDATE pg_database SET datistemplate = TRUE WHERE datname = 'template1';
\c template1
VACUUM FREEZE;
```
鍵をgithubに追加
```
rails master keyの取得
/config/master.key
```
```
install dotenv in rails
add .env file
add .env settings about DATABASE and secret_key_base
```

```
bitbucketに鍵を登録
```
```
webpackerのinstall
capistranoのinstall
database.ymlを設定して.envに
DATABASE_USERNAME
DATABASE_PASSWORD
RAILS_MASTER_KEY or SECRET_KEY_BASE
の設定
```
https://yarnpkg.com/en/docs/install#centos-stable
yum remove nodesource-release* nodejs
yum clean all
rm -rf /var/cache/yum/*
rm /etc/yum.repos.d/nodesource-el.repo
