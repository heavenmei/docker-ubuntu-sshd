## SSH-Enabled Ubuntu Docker Image

### Cloning the Repository

To get started, clone the GitHub repository containing the Dockerfile and scripts:

```bash
git clone XXX
cd ubuntu-sshd
```

### Building the Docker Image

Build the Docker image from within the cloned repository directory:

```bash
docker build -t my-sshd:latest .
```

### Running a Container

To run a container based on the image, use the following command:
（Default Password:root）
```bash
docker run -d --name mysshd -p 222:22 -e PASSWORD="123456" my-sshd:latest 
```
- `-d` runs the container in detached mode.
- `--name` container name
- `-p host-port:22` maps a host port to port 22 in the container. Replace `host-port` with your desired port.
- `-e PASSWORD=mysecretpassword` sets the SSH user's password in the container. Replace `mysecretpassword` with your desired password.
- `my-ubuntu-sshd:latest` should be replaced with your Docker image's name and tag.

To enter a container 
```bash
docker exec -it mysshd /bin/bash
```
- `-it` interactive in bash

### SSH Access

Once the container is running, you can SSH into it using the following command:

```bash
ssh -p host-port root@localhost
```

- `host-port` should match the port you specified when running the container.(222)

