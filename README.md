# Docker Remote API with TLS client authentication via container

 ca.pem
 cert.pem
 key.pem
 
The files cert.pem and key.pem are certificate and key for the client. The client will also need the ca.pem.

Run the Docker container using the command shown below.
```bash
$ chmod 666 /var/run/docker.sock
$ docker run --name dockertls -d -p 2376:443 -v <local cert dir>:/data/certs:ro -v /var/run/docker.sock:/var/run/docker.sock:ro marcomsousa/dockertls
```
