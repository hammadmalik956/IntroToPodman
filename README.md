# IntroToPodman
##Introduction to podman
Hello,
Podman is actually a daemonless, open source, Linux native tool designed to make it easy to find, run, build, share and deploy applications using Open Containers Initiative (OCI) Containers and Container Images.
It has a CLI similar to docker container engine. It is similar to docker but the difference is that it doesn’t have deamon running behind container layer
we can install podman using the following commands
sudo yum install -y podman
Checking if podman is working or not
sudo podman ps
Podman can run and download images from dockerhub no matter if the image is private or public.
for example
sudo podman run hello-world
we can check the image by following command
sudo podman image ls -a
seeing container , removing container ,removing image by following command
sudo podman ps -a

sudo podman rm d86089bc90b3

sudo podman image rm fce289e99eb9
we can do coding into it by coding in docker file
FROM centos:latest
RUN yum -y install httpd
CMD [“/usr/sbin/httpd”, “-D”, “FOREGROUND”]
EXPOSE 80
it is a simple httpd server running on centos machine
we can build it by following command
sudo podman build .
Now running it
sudo podman run -dit -p 80:80 
now that it is running test it if the repsonse is 200 (OK)
curl -I http://localhost:80
Podman provides every thing you could do with Docker but Docker Swarm
podman doesnot require central server to manage container
it communicates directly with the container runtime engine which provides enhanced security and reduces the attack surfaces by eliminating the need for daemon
Another advantage of Podman is that it can run containers as a non-root user which provides more security
Overall, Podman is a powerful and flexible tool for managing containers on Linux systems, providing users with increased security and flexibility compared to other container engines.
