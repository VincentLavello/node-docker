- Install Docker on Amazon EC2

	1.Update the installed packages and package cache on your instance.

	  sudo yum update -y
	
	2.Install the most recent Docker Community Edition package.

		sudo amazon-linux-extras install docker
		
		Or if an error occurs:
			sudo yum install docker
	
	3.Start the Docker service.

		sudo service docker start
	
	4.Add the ec2-user to the docker group so you can execute Docker commands without using sudo.

		sudo usermod -a -G docker ec2-user

		Log out and log back in again to pick up the new docker group permissions. You can accomplish this by closing your current SSH terminal window and reconnecting to your instance in a new one. Your new SSH session will have the appropriate docker group permissions.

	5.Verify that the ec2-user can run Docker commands without sudo.

		docker info

- Run Docker Container
	
	If everything above is done successfully, copy & paste the source code to the server through FTP or Git and navigate to the directory which contains Dockerfile and docker-compose.yml, and run these commands.

		docker-compose build
		docker-compose up -d

	You can check if the docker container is running using this command.

		docker ps