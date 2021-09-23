ANSIBLE-MYSQL-EXPORTER
=========

Deploy a Mysql-Exporter as a Docker container.

Requirements
------------

- Need to be Docker engine installed.
- A Mysql running to get Metrics from there.

Role Variables
--------------

- default_user: 'ubuntu'
- CONTAINER_NAME: "mysql-exporter"
- CONTAINER_STATE: 'started'
- IMAGE: 'prom/mysqld-exporter'
- BUILD: 'v0.13.0'
- MYSQL_HOST: 'localhost'
- MYSQL_PORT: 3306  
- MYSQL_USER: 'root'
- MYSQL_PASS: ''
- DOCKER_LOG_DRIVER: "json-file"
- DOCKER_LOG_OPTIONS: '{"max-size":"64m","max-file": "3"}'
- DOCKER_PUBLISHED_PORTS:
  - "0.0.0.0:9104:9104"

Dependencies
------------

None

Example Playbook
----------------


    - name: Deploy Mysql Exporter
      include_role:
        name: ansible-mysql-exporter
      vars:
        MYSQL_USER: "{{ MYSQL_ROOT_USERNAME }}"
        MYSQL_PASS: "{{ MYSQL_ROOT_PASSWORD }}"

License
-------

BSD

Author Information
------------------

Francisco Chantada
