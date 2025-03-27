# Basic-Dockerfile
https://roadmap.sh/projects/basic-dockerfile
Installing Docker on Ubuntu
Update the package index:

```bash
sudo apt update
```
Install the necessary packages to use the repository over HTTPS:

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
Add a GPG Docker key:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg / sudo apt-key add -
```
Add the Docker repository to APT sources:

```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release-cs) stable"
```
Update the package index again:

```bash
sudo apt update
```
Install Docker:

```bash
sudo apt install docker-ce
```
Launch and activate Docker:

```bash
sudo systemctl start docker
```
sudo systemctl enable docker
Make sure that Docker is installed and running:

```bash
sudo docker --version
```
(Optional) Add the user to the Docker group:
To run Docker commands without sudo, add your user to the docker group:

```bash
sudo usermod -aG docker $USER
```
After that, log out and log in again for the changes to take effect.

Create Dockerfile
```dockerfile
# Using the alpine base image
FROM alpine:latest

# Displaying a message to the console when starting the container
CMD ["echo", "Hello, Captain!"]
```
Save this code in a file called Dockerfile in the root directory of your project. To create a Docker image, run:

```bash
docker build -t my-captain-image .
```
After that, you can start the container with the created image:

```bash
docker run my-captain-image
```
