The following variables can be set in the settings.yml file.


## Webserver settings
  webserver_hostname: 'drupal.local'
  webserver_hostname_alias: 'www.{{ webserver_hostname }}'

## Vagrantfile configuration
  boxipaddress: "192.168.100.109"
  boxname: "vlad"
  host_synced_folder: "./docroot"

# Install components:
# - To install a component set it to "y".
# - To leave a component out of the install set the value to "n".

  adminer_install: "y"

  apache_install: "y"

  imagemagick_install: "n"

  mailcatcher_install: "n"

  memcached_install: "n"

  munin_install: "n"

  mysql_install: "y"

  node_install: "n"

  php_install: "y"

  pimpmylog_install: "y"

  redis_install: "n"

  ruby_install: "n" # Ruby is required by MailCatcher

  sendmail_install: "y"

  solr_install: "n"

  varnish_install: "n" # If you turn this off then make sure you set the http_port to be 80.

  xhprof_install: "n"

# Provision with custom playbooks
  custom_provision: "n"

# HTTP port for the web server. If you have turned off Varnish then you might want to set this to "80"
  http_port: 80

# HTTP port for the Varnish cache
  varnish_http_port: 80

# Administration email (used in instances when a server email is needed)
  admin_mail: 'test@example.com'

# PHP Settings
# PHP Version, can be one of "5.3" or "5.4"
# Vlad will error when a version that isn't understood is used
  php_version: "5.4"

# php.ini settings
  php_memory_limit: 512M
  php_max_execution_time: 60
  php_post_max_size: 100M
  php_upload_max_filesize: 100M
  php_display_errors: On
  php_display_startup_errors: On
  php_html_errors: On
  php_date_timezone: Europe/London

# Install PECL uploadprogress
  php_pecl_uploadprogress: "y"

# PHP APC Settings
  apc_rfc1867: '1'
  apc_shm_size: '256M'
  apc_shm_segments: '1'
  apc_num_files_hint: '0'

# MySQL Settings
  mysql_port: 3306
  mysql_root_password: sdfds87643y5thgfd
  server_hostname: vlad
  dbname: vladdb
  dbuser: vlad
  dbpass: wibble

# MySQL my.cnf settings
  mysql_max_allowed_packet: 128M
  innodb_file_per_table: innodb_file_per_table
  mysql_character_set_server: utf8
  mysql_collation_server: utf8_general_ci

# SSH Settings
  ssh_port: 22
# Add RSA or DSA identity from host to guest on 'vagrant up'.
# Does not support identites that require a passphrase. Options include:
# "n"           : don't add anything
# "y"           : add default files  (~/.ssh/id_rsa, ~/.ssh/id_dsa & ~/.ssh/identity)
# "[filename]"  : add a specific file e.g. /Users/username/.ssh/[filename]
  use_host_id: "n"

# Varnish Settings
  varnish_memory: 512

# Drupal Solr integration
# Select which Solr module to install
# accepted values are 'search_api_solr' or 'apachesolr'
  drupal_solr_package: "search_api_solr"

# Local hosts file location
# Default location on *nix hosts is '/etc/hosts'
# Default location for GasMask on OSX is '/Users/< username >/Library/Gas Mask/Local/< file >.hst'
  hosts_file_location: "/etc/hosts"

# Select weather Vlad should edit the hosts file.
  hosts_file_update: "y"

# Redis Port
  redis_port: 6379

# Set the level of verbosity that Ansible will use
# This can be one of "", "v", "vv", "vvv", or "vvvv"
  ansible_verbosity: ""

# Import MySQL database from file on 'vagrant up'. Options include:
# "n"          - don't import anything
# "y"          - import from vlad_aux/db_io/vlad_up.sql.gz
# "[filename]" - import from vlad_aux/db_io/[filename] (supports .sql, .bz2 and .gz files)
  db_import_up: "n"

# Add the default index.php file (useful to turn off if you are going git clone into the web root folder)
  add_index_file: "y"

# Git config user credentials (leave empty to skip this step)
  git_user_name: ""
  git_user_email: ""

# Use 'nfs' or 'rsync' for VM file editing in synced folder
  synced_folder_type: 'nfs'

# The OS that vlad will use. This can be:
# - "centos65"
# - "ubuntu12"
# - "ubuntu14"
# Defaults to "ubuntu".
  vlad_os: "centos65"