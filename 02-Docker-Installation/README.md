# Docker Installation

## Docker Installations on Amazon Linux
yum install docker -y

### Docker Instalaltion on Ubuntu

1. Add the necessary repository
The first thing to do is log in to your Ubuntu instance and add the necessary repository (as the version of Docker found in the standard repository isn't the latest community edition we want). Once you've logged in, add the official Docker GPG key with the command:

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
Next, add the official Docker repository:

echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
2. Install the necessary dependencies
We'll next install the required dependencies with the command:

sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release -y
3. Install Docker
Finally, update apt and install Docker with the following commands:

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
4. Add your user to the Docker group
In order to be able to use Docker without having to invoke it with sudo (which can lead to security issues), you must add your user to the docker group with:

sudo usermod -aG docker $USER
Log out and log back for the changes to take effect. 

Docker is now ready to use on your Ubuntu machine.

Testing the installation
Once Docker is installed, you can verify the installation by issuing the command:

docker version
In the output, you should see something like this:

Server: Docker Engine - Community
Engine:
  Version:          20.10.14


 
