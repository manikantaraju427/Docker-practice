### Docker-installtion on ubuntu server ###

### Update the package list to make sure you have the latest information about available packages: ###

$sudo apt-get update

### Install the necessary packages to allow apt to use a repository over HTTPS and install packages from the Docker repository: ###

$sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common

### Add Docker's official GPG key to ensure the integrity of the packages: ###

$curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg


### Add the Docker repository to your system's sources list: ###
### For Ubuntu 20.04 LTS (Focal Fossa): ###

$echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu focal stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

### For Ubuntu 18.04 LTS (Bionic Beaver): ###

$echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu bionic stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

### Update the package list again to include the Docker repository: ###

$sudo apt-get update

### Finally, install Docker: ###

$sudo apt-get install -y docker-ce docker-ce-cli containerd.io

### Docker should now be installed. You can check its status and version with: ###

$sudo systemctl status docker
$docker --version

### If it's not running, you can start it using: ###

$sudo systemctl start docker


### Verify that the Docker Engine installation is successful by running the hello-world image. ###

$sudo docker run hello-world

### Optionally, if you want to run Docker commands without using sudo, you can add your user to the docker group: ###

$sudo usermod -aG docker $USER

### Log Out and Log Back In ###

$logout    

### Verify Group Membership: After logging back in, open a terminal and verify that your user is a member of the "docker" group using the "groups" command: ###

$groups $USER



### After logging back in and ensuring that the Docker service is running, you should be able to run Docker commands without sudo ###







