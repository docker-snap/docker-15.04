# Docker Framework

This is the Docker application deployment mechanism.

AppArmor profiles have been moved to `/var/lib/apparmor/profiles`, default profile has been modified.

Data is stored in `/var/lib/apps/docker/${version_of_snap_package}/` (symlinked to `/var/lib/apps/docker/current`).

If you need to pass through proxies or adjust default DNS for your containers, edit `/apps/docker/current/etc/docker.conf` accordingly and restart the Docker daemon service:

    FTP_PROXY=http://your.proxy:3128
    HTTP_PROXY=http://your.proxy:3128
    HTTPS_PROXY=http://your.proxy:3128
    DOCKER_OPTIONS="--dns 8.8.8.8"

Restarting the daemon can be accomplished via `sudo systemctl restart docker_docker-daemon_${version_of_snap_package}.service`.

If you need privileged access in containers (`docker run --privileged`), you can issue `docker-privilege on` (disable again with `docker-privilege off` and check the current configuration with `docker-privilege status`); however, be forewarned: the confinement will be nearly nonexistent (full root access to the host system is possible).
