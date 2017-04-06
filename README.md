##playbook
  ansible databases -a "cat /etc/*elease"
- hosts: destinations
  user: root
  tasks:
- name: Install mariaDB repository
  apt_repository: repo='deb http://ftp.igh.cnrs.fr/pub/mariadb/repo/10.0/ubuntu trusty main' state=present
- name: Add repository key to the system
  apt_key: keyserver=keyserver.ubuntu.com id=0xcbcb082a1bb943db
- name: Install MariaDB Server
  apt: name=mariadb-server state=latest update_cache=yes
