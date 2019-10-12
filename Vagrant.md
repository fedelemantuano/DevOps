# Vagrant

    # Create a dir and create a project in it with init
    vagrant init generic/rhel7
    vagrant box add generic/rhel7                        # will ask to choose choose PROVIDER image
    vagrant box add generic/rhel7 --provider virtualbox  # choose virtualbox image
    
## Add ssh keys

Generate a ssh key (id_rsa_vagrant) and place it in the same folder as the vagrant file  
This is usefull for testing Ansible playbooks and to use WSL.  
Modify the vagrant file to include the provisioning step that will add the key tu default user vagrant and root:

      config.vm.provision "file", source: "id_rsa_vagrant.pub", destination: "/home/vagrant/.ssh/authorized_keys_new"
      config.vm.provision "shell", inline: <<-EOC
        cat /home/vagrant/.ssh/authorized_keys_new >> /home/vagrant/.ssh/authorized_keys
        sudo mkdir /root/.ssh/
        sudo cat /home/vagrant/.ssh/authorized_keys_new > /root/.ssh/authorized_keys
      EOC
      
## WSL Notes  (Windows Subsystem for Linux)

Install the vagrant software in the WSL too (after having installed on windows) and set this env var to tell vagrant inside WSL to use Virtualbox in Windows:

    export VAGRANT_WSL_ENABLE_WINDOWS_ACCESS="1"

make sure to create the file /etc/wsl.conf and past thi inside:

    [automount]
    enabled = true
    options = "metadata,umask=0022,fmask=0022"
