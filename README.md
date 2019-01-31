# dockerservice-openrc
## Run docker-compose services as openrc services
Copy the script dockerservice to `/etc/init.d/dockerservice`. Each docker-compose based service `$SERVICENAME` must exist like so: `/root/docker/$SERVICENAME/docker-compose.yml`. Finally create some symbolic link `/etc/init.d/dockerservice.$SERVICENAME` pointing to `/etc/init.d/dockerservice`. Services can now be started/stopped via e.g. `/etc/init.d/dockerservice.gitea start`.
