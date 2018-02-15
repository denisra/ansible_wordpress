Wordpress
=========

Playbook to deploy Wordpress containers on multiple hosts with a MYSQL DB server and a NGINX reverse proxy.

Requirements
------------

In this example, we are using an invetory file with the following structure:

```
[app_servers]
app1 ansible_host=x.x.x.x ansible_ssh_private_key_file=ssh_pvt.key
app2 ansible_host=x.x.x.x ansible_ssh_private_key_file=ssh_pvt.key

[db_servers]
db1 ansible_host=x.x.x.x ansible_ssh_private_key_file=ssh_pvt.key

[proxy_servers]
proxy1 ansible_host=x.x.x.x ansible_ssh_private_key_file=ssh_pvt.key

```

Role Variables
--------------

All global variables are defined in `group_vars/all`:

```
group_vars/all:
  project_name: Project name
  db_master_password: DB password
  default_db: Default DB name
  app_instances_per_host: Number of containers per host
```

We also have app_servers, db_servers and proxy_servers variables defined. Each of these files will have a docker_image variable, where we declare the image that we want to use for each service. The rest of the variables are self-explanatory.


Example Playbook
----------------

The `deploy_wordpress.yml` playbook has all the tasks to deploy all services. Please have a look at it for more information.

License
-------

BSD

Author Information
------------------
Denis Afonso
