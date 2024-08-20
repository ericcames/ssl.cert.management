aap_cert_renewal
=========

This role will install renew and install ssl certs into legacy ansible and containerized ansible.  The role uses tags to control what tasks are executed.
```
For original platform use the legacy tag.
- legacy

For the containerized platform use the container tag.
- container
```

Requirements
------------
- certbot ssl cert

Role Variables
--------------
```
aap_cert_renewal_vault_file_name: ames_vault.yml
aap_cert_renewal_secret_file_name: ames_secret.yml
aap_cert_renewal_controller_url: aap.kona.services
```

Dependencies
------------

Example Playbook
----------------

---
- name: Install Ansible Automation Platform
  hosts: aap.kona.services

  roles:
    - role: aap_cert_renewal

License
-------

https://opensource.org/license/mit
