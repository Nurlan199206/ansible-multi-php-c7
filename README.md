# nginx-php-fpm installation on CentOS 6/7.

Software version.

Ansible 2.7.5

Centos 6/7

php 7.0/7.1/7.2/7.3

nginx 1.14

MariaDB Ver 15.1 Distrib 5.5.60


run setup.sh or: 

``` yum install git ansible mc python2-PyMySQL -y ```

and

``` ansible-playbook --connection=local -s /etc/ansible/roles/ansible-multi-php-c7/nginx.yml ```

for ansible 2.8.x versions
``` ansible-playbook --connection=local /etc/ansible/roles/ansible-multi-php-c7/nginx.yml ```


for successfully run playbook, dont forget add in ```/etc/ansible/ansible.cfg after [defaults]```

```invalid_task_attribute_failed=False```


for switching PHP versions, change line in ```/etc/nginx/conf.d/default.conf```

``` fastcgi_pass   127.0.0.1:9000; ``` to ```127.0.0.1:9001``` ```127.0.0.1:9002``` etc...

or create new virtual host



