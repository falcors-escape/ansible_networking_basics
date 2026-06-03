This is a basic overview of how to get ansible working to connect to old cisco gear (Cisco 2800 series routers from a RHEL 10 control machine)

1) install ansible
    sudo dnf install -y ansible-core
2) install ansible netcommon and cisco IOS specific plugins and modules
    ansible-galaxy collection install ansible.netcommon
    ansible-galaxy collection install cisco.ios
3) Make an inventory file
4) Make a group_vars directory with the appropriate subdirectory system to get ansible to read vault files.
5) Create  avault.yml file that will hold usernames and passwords
6) encryp the file using the ansible-vault command
    ansible-vault encrypt group_vars/vault.yml
7) Link the vault to your group variables using the "{{ variable }}" syntax in the group_vars file
8) Create a simple ping playbook
9) test
    ansible-playbook -i hosts playbook/ping.yml --ask-vault-pass

