```zsh
docker build -t ctf1 .
docker run -i -t --name ctf1 --cap-add=SYS_PTRACE --security-opt="seccomp=unconfined" ctf1 /bin/bash
docker exec -it ctf1  bash -p
```
