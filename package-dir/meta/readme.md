Docker Framework


This is the docker app deployment mechanism.

Actual docker version: 1.3.2.

Apparmor profiles have been moved to /var/lib/apparmor/profiles.
Data is stored in /var/lib/apps/docker/${version_of_snap_package}/.

If you need to pass through proxies or dns, edit /apps/docker/current/etc/docker.conf accordingly and restart the docker service:
i.e:
FTP_PROXY=http://your.proxy:3128
HTTP_PROXY=http://your.proxy:3128
HTTPS_PROXY=http://your.proxy:3128
DOCKER_OPTIONS="--dns 8.8.8.8"

sudo systemctl restart docker_docker_${version_of_snap_package}.service
