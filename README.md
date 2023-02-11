<<<<<<< HEAD
=======
project 11 new
adjusted now
new nw




<!-- ############################################
=======================================================================
site.yml freestyle
---
# - hosts: all
# - name: Include dynamic variables 
#   tasks:
#   import_playbook: ../static-assignments/common.yml 
#   include: ../dynamic-assignments/env-vars.yml
#   tags:
#     - always

# -  hosts: webservers
# - name: Webserver assignment
#   import_playbook: ../static-assignments/webservers.yml

 - name: Loadbalancers assignment
       hosts: lb
         - import_playbook: ../static-assignments/loadbalancers.yml
        when: load_balancer_is_required
======================================================================================== -->



<!-- ---
# Variable setup.
- name: Include OS-specific variables.
  include_vars: "{{ ansible_os_family }}.yml"

- name: Define nginx_user.
  set_fact:
    nginx_user: "{{ __nginx_user }}"
  when: nginx_user is not defined

# Setup/install tasks.
- include_tasks: setup-RedHat.yml
  when: ansible_os_family == 'RedHat' or ansible_os_family == 'Rocky' or ansible_os_family == 'AlmaLinux'

- include_tasks: setup-Ubuntu.yml
  when: ansible_distribution == 'Ubuntu'

- include_tasks: setup-Debian.yml
  when: ansible_os_family == 'Debian'

- include_tasks: setup-FreeBSD.yml
  when: ansible_os_family == 'FreeBSD'

- include_tasks: setup-OpenBSD.yml
  when: ansible_os_family == 'OpenBSD'

- include_tasks: setup-Archlinux.yml
  when: ansible_os_family == 'Archlinux'

# Vhost configuration.
- import_tasks: vhosts.yml

# Nginx setup.
- name: Copy nginx configuration in place.
  template:
    src: "{{ nginx_conf_template }}"
    dest: "{{ nginx_conf_file_path }}"
    owner: root
    group: "{{ root_group }}"
    mode: 0644
  notify:
    - reload nginx

- name: Ensure nginx service is running as configured.
  service:
    name: nginx
    state: "{{ nginx_service_state }}"
    enabled: "{{ nginx_service_enabled }}" -->
>>>>>>> feature/jenkinspipeline-stages
