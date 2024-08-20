ansible_platform_install
=========

This role will install and configure legacy ansible and containerized ansible.  The role uses tags to control what tasks are executed.
```
For original platform use the legacy tag.
- legacy

For the containerized platform use the container tag.
- container
```

Requirements
------------
- [Get Red Hat Offline Token](https://access.redhat.com/management/api "Red Hat Offline Token")
- [Download Red Hat Ansible Automation Platform SHA Value](https://access.redhat.com/downloads/content/480/ver=2.4/rhel---9/2.4/x86_64/product-software "Download Red Hat Ansible Automation Platform")

Role Variables
--------------

**All installs**
```
ansible_platform_install_vault_file_name: ames_vault.yml
ansible_platform_install_secret_file_name: ames_secret.yml
ansible_platform_install_containerized_controller_url: testaap.kona.services
```
- [Get Red Hat Offline Token](https://access.redhat.com/management/api "Red Hat Offline Token")
```
ansible_platform_install_offline_token: 123456
```
- [Download Red Hat Ansible Automation Platform](https://access.redhat.com/downloads/content/480/ver=2.4/rhel---9/2.4/x86_64/product-software "Download Red Hat Ansible Automation Platform") <br>

**Legacy Install**
```
ansible_platform_install_aap_non_container_bundle_sha_value: "730c4b831a8c1cddd0a7023db2dd1159d0aebd2dc81921fe3224999d771b5dfb"
```
**Containerized Install**
```
ansible_platform_install_aap_bundle_sha_value: "0781cab21cd21992a22bb8ed6f9b1018dff0d092d5882e1e9aafbd48337f6662"
ansible_platform_install_manifest_file_name: manifest_Zigfreed_20240528T153016Z.zip
ansible_platform_install_controller_postinstall_repo_url: https://github.com/ericcames/aap.controller.config.git
ansible_platform_install_hub_postinstall_repo_url: https://github.com/ericcames/aap.automation_hub.config.git
```

Dependencies
------------

Example Playbook
----------------

---
- name: Install Ansible Automation Platform
  hosts: control

  roles:
    - role: ansible_platform_install

License
-------

https://opensource.org/license/mit
