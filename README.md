# class6-Assignment

Create User Accounts for All Team Members on the Ubuntu Server


Owned by njomgang benla bertrand

To create user accounts for all team members on an Ubuntu server, follow these steps:

Log into your server 

Use SSH to log into your server as the root user or a user with sudo privileges.

 

Copy code

ssh username@server_ip

Create user accounts:

Use the adduser command to create a new user. Replace username with the actual username of the team member.

 

Copy code

sudo adduser username

This command will prompt you to enter a password and fill in other user details. Repeat this step for each team member.

Set up SSH keys 

For better security, use SSH keys instead of passwords. Here’s how to set up SSH keys for a user:

Generate an SSH key pair on the client machine:

Copy code

ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

This will generate a public key (id_rsa.pub) 

Copy the public key to the server:

 

Copy code share via slack

 

Alternatively, you can manually add the public key to the ~/.ssh/authorized_keys file on the server.

Copy code

sudo mkdir -p /home/username/.ssh sudo touch /home/username/.ssh/authorized_keys sudo vi /home/username/.ssh/authorized_keys

Paste the public key into the authorized_keys file, then set the appropriate permissions:

 

Copy code

chmod 400 authorized_keys

Verify the new user accounts:

Log out of the server and try logging in with the new user accounts to ensure they are set up correctly.
