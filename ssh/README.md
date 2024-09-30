Step 3: Configure SSH config file for SSHing into the servers
In the ~/.ssh/ directory, create a config file that simplifies the SSH process for this scenario:

Explanation of the Config File:

Host: This section defines the connection to your server. The HostName is the public/private IP of the server
User: Ubuntu by default if your have launched an ubuntu instance. Change accordingly to your requirement.
IdentityFile: specifies the private key used for authentication. Change the location of your key file accordingly.

Test SSH connection
From local machine SSH into nginx instance:

You can also set the hostname of the instances by run these commands

Nginx instance

sudo hostnamectl set-hostname nginx
