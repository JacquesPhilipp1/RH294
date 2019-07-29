1. INTRODUCTION TO ANSIBLE VARIABLES
  - Used to store values that can be reused through your play
  - Useful for things like users, services

2. Naming vars
  - Only alpha numeric and underscores

3. Defining vars
  - Explain presidence
  - global
  - play
  - host

4. variables.yml

5. host_vars and group_vars DIRS

6. Command line vars override all
  - ansible-playbook main.yml -e "package=apache"

7. Arrays
  - array.yml

8. Register and Debug
  - register_debug.yml

==== Day 2 ===

1. Vaults.
  # Create
  - ansible-vault create secret.yml

  # Same but on one line using a password file. Password file needs to be carefully protected.
  - ansible-vault create --vault-password-file=vault-pass secret.yml

  # View
  - ansible-vault view secret.yml

  # Edit
  - ansible-vault edit secret.yml

  # Encrypt a file that already exists
  - ansible-vault encrypt file.yml
  - ansible-vault encrypt file.yml --output=file_crypt.yml

  # Decrypting an Existing File
  - ansible-vault decrypt secret.yml
  - ansible-vault decrypt secret.yml --output=file_crypt.yml

  # Changing the Password of an Encrypted File
  - ansible-vault rekey secret.yml
  - ansible-vault rekey --new-vault-password-file=pass.yml secret.yml


2. Vault passwords in play
   # you need to provide the encryption password to the ansible-playbook
   - ansible-playbook --vault-id @prompt site.yml 

   # Older syntax
   - ansible-playbook --ask-vault-pass site.yml

   # Else you can provide a pass file
   - ansible-playbook --vault-password-file=vault-pw-file site.yml

3. Keep seperate dirs for crypt data vs normal data
   # You can use multiple host_vars/servera/vars & host_vars/servera/vault

### Guided Excercise ###

4. Facts
   # Demo play on getting all the facts
   - facts_printall.yml

   # Ansible substitues vars
   - facts_using.yml

   # Older versions of Ansible use facts injected as vars instead of namespace. 
   # new ansible_facts['distribution']  VS old ansible_distribution
   # You can get this old format running setup module
   - ansible servera -m setup

   # Turn off fact gathering
   - facts_no-gather.yml

   # Custom facts in /etc/ansible/facts.d/.fact
   - vim /etc/ansible/facts.d/custom.fact
     [names]
     first=Jacques
     last=Philipp
   - facts_custom.yml

   # Magic vars are vars set automatically by ansible but are not facts
   # Most common
   - hostvars # all hosts variables without facts
	ansible servera -m debug -a 'var=hostvars["servera"]'
   - group_names # all inventory groups
   - groups # Lists all groups and hosts in the inventory.
   - inventory_hostname  # The name in inventory can be different from fqdn


   - 

