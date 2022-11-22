Apache Zookeeper Standalone Setup through Ansible.
==================================================

Pre requisites:
===============
	1. ZK User and ZK Group should be created.
	2. ZK User should have the sudo privilege to setup zookeeper.
	3. Ansible should be installed on control Node/VM.
	3. Ansible Control Node should have the internet access to download the zookeeper tarball from official zookeeper repository.
	4. OpenJDK-1.8 should be pre-installed on ZK server/VM.
	5. Copy the zookeeper, myhosts, main.yml from github to the Ansible Control Server/VM.
	6. Update the ZK server hostname in inventory 'myhosts'.

Execution:
==========
	1. Execute the ansible playbook as mentioned below.
		
		ansible-playbook -i myhosts main.yml

	2. Enter the ZK User.			[Example: ec2-user]
	3. Enter the ZK Group.			[Example: ec2-user]
	4. Enter the ZK Version.		[Example: 3.5.5]
	5. Enter the ZK Installation Path.	[Example: /opt]
	6. Enter the ZK Data Directory.		[Example: /opt/zookeeper/data]

Validation:
===========
	1. Ensure 'zookeeper' directory is present under ZK Installation Path.
	2. Ensure 'data' directory is exist on ZK Data Directory.
	3. Validate 'myid' file is exists on 'data' directory and contains the ZK Server id as '1'.

Actions:
========
	1. zookeeper-server staus 	==> sudo systemctl status zookeeper.service
	2. zookeeper-server start	==> sudo systemctl start zookeeper.service
	3. zookeeper-server stop	==> sudo systemctl stop zookeeper.service
	4. zookeeper-server restart 	==> sudo systemctl restart zookeeper.service

