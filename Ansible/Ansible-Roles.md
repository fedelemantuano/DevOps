# Ansible Roles

    cd <role-base-folder>                             # maybe a git repo folder
    ansible-galaxy init <ansible-role-name> --force   # force if an empty git repo
    vi tests/ansible.cfg
    >>[defaults]
    >>roles_path = ../../
    chmod 600 tests
    cd tests                                          # role test folder
    vagrant init generic/rhel7
    vagrant box add generic/rhel7 --provider virtualbox
  
