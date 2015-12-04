"A Certification Framework for Cloud-based Services"


Information for reviewers
This page contains the links to the code of our certification framework components and all certification artifacts at their basis.

A running version of our sytem is available [here](http://159.149.70.50:3000/index.html)

Software

	Software is available at:
	
	- [Test Manager] (http://github.com/)

	- [Test Agent]   (http://github.com/)

	sorry, url were anonymezed.

XML SCHEMA
	
	CMTemplate.xsd
	Certification Model Template XML Schema

	CommonPartsCM.xsd
	Dependency for Test Based Certification Schema

	slasoi.xsd
	Dependency for Test Based Certification Schema

	testbasedCM.xsd
	Test Based Certification XML Schema

XML FILE
	
	CertifcationModel_example.xml
	Certification Model for the example explained in the paper.




Probe


	filesystem_checker.py
	it tests file confidentiality in file system.
	It checks if CHMODs is equal to that ones defined in the input config file.
	It tries to access to the target file both in read and write modes, checking effectively that chmods are respected and not manipulated in some way.
	The input file describes a FSM that gets:
	
		[0]
		host=hostnameOfServer						#the hostname of the server to connect to through SSH
		port=22										#SSH port for the server above
		ssh_key_path=ssh_private_key				#SSH private key. The public key has to be on the server before launching the test
		ssh_server_key_path=ssh_public_key			#SSH public key of the server, to authenticate it

		[1]
		filepath=/file/to/verify					#absolute path  of the target file
		chmod=600									#chmods

		[2]
		username_owner=usernameOwner				#username of the owner

		[3]
		username_group=usernameGroup				#username of a user that is in the same unix group of the owner

		[4]
		username_other=usernameOther				#username of another user that isn't in the same unix group of the owner

	The third users specified above must have testAgent's ssh public key in their ~/.ssh/authorized_keys file


