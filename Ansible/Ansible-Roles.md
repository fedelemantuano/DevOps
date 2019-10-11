# Ansible Roles

    cd <role-base-folder>                             # maybe a git repo folder
    ansible-galaxy init ansible-role-motd --force     # force if an empty git repo
    cd tests                                          # role test folder
    vagrant init generic/rhel7
    vagrant box add generic/rhel7 --provider virtualbox
  
