# Task 2
- Create an ansible playbook for user administration in linux servers.
	- Add the ability to add and delete users and groups as well as to add and remove users from groups.
	- Use a variable file to controls which users need to created ,added to group etc.
	- Use roles in your playbook with a custom role directory
### Directories used under role of user_administation are:
	- files/: This directory is used to store static files that need to be transferred to the target hosts. These files are typically copied directly without modification.
	- tasks/: This directory contains YAML files defining the main tasks of the role. These tasks define the actions that the role should perform on the target hosts.
	- vars/: This directory contains YAML files defining variables used by the role. Unlike default variables, these variables are not meant to be overridden by users and are typically used for internal role configuration.

ansible-playbook playbook.yml -u client --ask-become-pass --tags addgroup

### order for execution of tags for proper adminstration
Tags
	- addgroup
	- adduser
	- adduserafter
	- addusertogroup
	- removeuserfromgroup
	- removegroup
	- removeuser

#### error faced
- errors
	- [x] removeuserfromgroup is not working as desired
	- [x] unable to login into user4,5,6
	- [x] adduser worked before adding groups, but not now; throwing error of group not existing getent group
		- groups should be created before
	- [ ] delete the user directories from /home dir , (these directories are not deleted even after the user is deleted )
