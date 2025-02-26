# ## kubectl Setup

## Setup kubectl command line utility


- install kubectl command line utility first to manage Kubernetes resources 
- Reference documentation -->  [﻿kubernetes.io/docs/tasks/tools/](https://kubernetes.io/docs/tasks/tools/) 


### Install kubectl binary with curl on Linux


- [ ] Download the latest release with the command: 
```
apt install curl
```
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```


![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/EAidEx9cky96ET5hPSoD0.png?ixlib=js-3.7.0 "image.png")

- [ ] to download the specific version , replace the `$(curl -L -s https://dl.k8s.io/release/stable.txt)` portion of the command with the specific version.
- [ ] For example, to download version 1.32.0 on Linux x86-64, type:
```
curl -LO https://dl.k8s.io/release/v1.32.0/bin/linux/amd64/kubectl
```
- [ ] Validate the binary (optional) , Download the kubectl checksum file:
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
```
- [ ] Validate the kubectl binary against the checksum file: 
```
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
```
- [ ] If valid, the output is: `﻿``kubectl: OK` 
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/dres7muLERw2R0Rvmld-0.png?ixlib=js-3.7.0 "image.png")

- [ ] If the check fails, `sha256`  exits with nonzero status and prints output similar to:
```
﻿kubectl: FAILED
sha256sum: WARNING: 1 computed checksum did NOT match 
```
- [ ] Install kubectl
```
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
- [ ] Test to ensure the version you installed is up-to-date:
```
kubectl version --client
```
- [ ] For detailed information 
```
kubectl version --client --output=yaml
```
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/voSIboWBozCgvyPmU6Szf.png?ixlib=js-3.7.0 "image.png")

- [ ] If you do not have root access on the target system, you can still install kubectl to the `~/.local/bin`  directory:
```
chmod +x kubectl
mkdir -p ~/.local/bin
mv ./kubectl ~/.local/bin/kubectl
# and then append (or prepend) ~/.local/bin to $PATH
```
### Install using native package management


- [ ] refer --> [﻿kubernetes.io/docs/tasks/tools/install-kubectl-linux/](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/) 


