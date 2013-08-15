deploy-gitlab
=============

Deploy gitlab to a vanilla ubuntu 12.04.2 64bit server.

- Install Ubuntu with OpenSSH server
- Connect with ssh and install chef client

```
~$ curl -L https://www.opscode.com/chef/install.sh | sudo bash
```

- Install git

```
~$ sudo apt get install
```

- Clone this repository

```
~$ git clone https://github.com/pghalliday/deploy-gitlab.git
```

- Run the recipe

```
~$ cd deploy-gitlab
~/deploy-gitlab$ chef-solo -c solo.rb -j solo.json
```
