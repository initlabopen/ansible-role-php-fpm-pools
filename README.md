Ansible Role: PHP-FPM-POOLS
=========

Ansible role for PHP-FPM pools configuration.

Requirements
------------

Must be running PHP-FPM
A restart php-fpm handler is used to restart PHP-FPM after configuration changes and must be defined in your playbook

Role Variables
--------------

- php_fpm_pools: List of php-fpm pools
  - **name**: Name of php-fpm pool file
  - **user**: User for pool's processes
  - **group**: Group for pool's processes
  - **listen**: Port for php-fpm
  - Othen directives - List of pool directives http://php.net/manual/en/install.fpm.configuration.php


- **php_fpm_pool_defaults**: List of default pool directives applied for every php-fpm pool
  - **pm**: dynamic
  - **pm.max_children**: 5
  - **pm.start_servers**: 2
  - **pm.min_spare_servers**: 1
  - **pm.max_spare_servers**: 3
  - **pm.status_path**: /status

- **php_fpm_default_pool**:
  - **delete**: yes - Delete default php-fpm pool.
  - **name**: www.conf - Default name for php-fpm pool.

**php_fpm_pools_directory**: "/etc/php5/fpm/pool.d" - php-fpm pool directory path

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: initlabopen.php-fpm-pools}

License
-------

BSD

Author Information
------------------

Roman Agabekov <r.agabekov@gmail.com>

# ansible-role-php-fpm-pools
