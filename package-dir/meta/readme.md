Docker Framework
This is the docker app deployment mechanism.

Apparmor profiles have been moved to /var/lib/apparmor/profiles, default profile has been modified.
Data is stored in /var/lib/apps/docker/${version_of_snap_package}/.

If you need to pass through proxies or dns, edit /apps/docker/current/etc/docker.conf accordingly and restart the docker service:
i.e:
FTP_PROXY=http://your.proxy:3128
HTTP_PROXY=http://your.proxy:3128
HTTPS_PROXY=http://your.proxy:3128
DOCKER_OPTIONS="--dns 8.8.8.8"

If you need privileged access, you can issue 'docker-privilege on'. But the confinement will be nearly nonexistent.

Docker can read and write to your `$HOME/apps/docker/**` directory, place your Dockerfile there.
