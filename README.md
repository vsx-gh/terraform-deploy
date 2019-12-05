terraform-deploy
=========

Fetch the most recent version of Terraform from Hashicorp; update if present, install if not

Requirements
------------

wget

Role Variables
--------------

defaults:
install_loc: "{{ ansible_env.HOME }}/.local/bin/"
terraform_owner: "{{ ansible_env.USER }}"
terraform_group: "staff"
terraform_perms: "0700"

Example Playbook
----------------

    # Use `become` if setting user and/or group ownerships to `root` or installing to a location requiring it
    - hosts: servers
      become: yes
      roles:
         - { role: vsx_gh.terraform-deploy, install_loc: /usr/local/bin, terraform_owner: root, terraform_group: root, terraform_perms: "0755" }

    # Use defaults
    - hosts: servers
      roles:
         - { role: vsx_gh.terraform-deploy }

License
-------

MIT

Author Information
------------------

Jeff VanSickle
jeffvansickle.com
