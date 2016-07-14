We leverage the newer-style `snapcraft`-based build for building Docker here.  You will need both an `amd64` and an `armhf` 16.04+ host with functional `snapcraft` in order to compile binaries for this 15.04-style snap.

```console
$ git clone --single-branch https://github.com/infosiftr/snap-docker.git
$ cd snap-docker
$ ./build-static-bins.sh
```

When finished, copy the contents of the `static-bins` directory, replacing either `package-dir/bin/amd64` or `package-dir/bin/armhf` (as appropriate).