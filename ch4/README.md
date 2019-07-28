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
