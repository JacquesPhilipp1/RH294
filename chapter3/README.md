1. .vimrc
	- autocmd FileType yaml setlocal et ai ts=2 sw=2 sts=0 cursorcolumn

2. Compare ad-hoc to play
	- ansible servera -m user -a 'user=bob state=present'
	- useradd.yml

3. Explain more about YAML, key: value, lists and indentation in useradd.yml

4. run useradd.yml and explain output
	- show how to increase verbosity -v -vv -vvv

5. multi-task.yml
	- Show how multiple tasks can be added to the play and execute in order.

6. Syntax checking
	- ansible-playbook --syntax-check multi-task.yml
	- Dry run ansible-playbook -C multi-task.yml

7. multi-play.yml
	- Show indentation of top level items
	- show how each play can have it's own remote_user, become etc

8. Ansible Module Documentation
	- https://docs.ansible.com
	- ansible-doc -l
	- ansible-doc copy
	- ansible-doc -s copy

5. Syntax variations
	- Comments #
	- 'String don't have to be in '' but it's good practice'
	- strings.yml to demo line wrap
	- Show variations on syntax in student-guide



	
