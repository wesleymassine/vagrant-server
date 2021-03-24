# Servidor Mysql em vagrant

* Install Vagrant
[Documentação](https://www.vagrantup.com/docs/vagrantfile).

[Buscando-Boxes](https://app.vagrantup.com/boxes/search).

- Se o VirtualBox não estiver instalado em seu sistema, você pode instalá-lo executando:

```bash
sudo apt update
sudo apt install virtualbox

```

- Baixe o pacote Vagrant com wget :

```bash
curl -O https://releases.hashicorp.com/vagrant/2.2.9/vagrant_2.2.9_x86_64.deb
```

- Depois de fazer o download do arquivo, instale-o digitando:

```bash
sudo apt install ./vagrant_2.2.9_x86_64.deb
```
- Verifique a versão do Vagrant:
```bash
vagrant --version
```

- Primeiros Passos
```bash
mkdir ~/my-vagrant-project
cd ~/my-vagrant-project

vagrant init
```

- Após configurar seu Vagrantfile

```bash
vagrant up
```
- Para fazer o SSH na máquina virtual, execute:
```bash
vagrant ssh
```
- Você pode parar a máquina virtual com o seguinte comando:

```bash
vagrant halt
```

```bash
vagrant status
```
```Output:
Current machine states:

mysqlserver               running (virtualbox)

The VM is running. To stop this VM, you can run `vagrant halt` to
shut it down forcefully, or you can run `vagrant suspend` to simply
suspend the virtual machine. In either case, to restart it again,
simply run `vagrant up`.
```

- Para destruir todos os recursos criados durante a criação da máquina, digite:
```bash
vagrant destroy -f
```

## Testando o MySQL

vagrant@precise64:~$ mysql --version
mysql  Ver 14.14 Distrib 5.5.54, for debian-linux-gnu (x86_64) using readline 6.2
vagrant@precise64:~$ mysql -u root -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 46
Server version: 5.5.54-0ubuntu0.12.04.1 (Ubuntu)

Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| myDB               |
| mysql              |
| performance_schema |
+--------------------+
4 rows in set (0.00 sec)

mysql>  


