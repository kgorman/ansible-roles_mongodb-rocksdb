ansible-roles_mongodb-rocksdb
=========

Installs [MongoDB](http://www.mongodb.org) and starts up a nice base configuration using the [RocksDB](http://rocksdb.org/blog/1967/integrating-rocksdb-with-mongodb-2/) engine developed by Facebook including base security and base settings for high performance.

It should be noted this builds RocksDB and MongoDB from source, so it takes a *while* to build.

More info on [RocksDB here](https://github.com/mongodb-partners/mongo-rocks).

Role Variables
--------------

You will want to hack on the variables in defaults/main.yml to fit your liking. Things you will most likely want to change are:

```yaml
# The port for mongodb server
mongodb_port: 9005

# The directory prefix where the database files would be stored
mongodb_datadir_prefix: /data/mongodb/

# The password for admin user
mongodb_admin_pass: xxx

# The password for admin user
mongodb_admin_user: yyy

```

Install
-------
[See here](https://galaxy.ansible.com/intro)

Example Playbook
----------------

To use this simply setup a YAML file for running:

```yaml
$>cat test.yml
---
- hosts: mongoservers
  roles:
  - { role: ansible-roles_mongodb-rocksdb }
```

```yaml
$>cat hosts.txt
[mongoservers]
0.0.0.0
```

and execute like:
```bash
$>ansible-playbook -i hosts.txt test.yml
```

Testing and Requirements
------------------------
This role is tested on Rackspace [onMetal High I/O](http://www.rackspace.com/cloud/servers/onmetal/) servers with Centos 7.

```
uname -a | awk '{print $3}'
3.10.0-123.el7.x86_64
```

License
-------

BSD

Author Information
------------------
[Twitter](http://www.twitter.com/kennygorman)

[Github](https://github.com/kgorman)
