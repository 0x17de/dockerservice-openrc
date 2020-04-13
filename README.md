# dockerservice-openrc
## Run docker-compose services as openrc services
Copy the script dockerservice to `/etc/init.d/dockerservice`. Each docker-compose based service `$SERVICENAME` must exist like so: `/root/docker/$SERVICENAME/docker-compose.yml`. Finally create some symbolic link `/etc/init.d/dockerservice.$SERVICENAME` pointing to `/etc/init.d/dockerservice`. Services can now be started/stopped via e.g. `/etc/init.d/dockerservice.gitea start`.

The directory containing the service directories can be overridden by setting the variable `SUBCFGDIR`.  This can be set for a specific service in its `/etc/conf.d/dockerservice.$SERVICENAME` file, or the default may be changed by setting it in `/etc/rc.conf` or an `/etc/rc.conf.d` file.

Alternatively, the complete path to the docker-compose input file may be specified by setting SUBCFG in the services's `/etc/rc.conf.d` file.  The value of this variable is passed to the `-f` option of `docker-compose`.
