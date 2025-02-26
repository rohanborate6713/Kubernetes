# K8S cluster Setup using -->  Minikube



## Install Minikube


- Reference documentation --> [﻿minikube.sigs.k8s.io/docs/start/?arch=%2Fwindows%2Fx86-64%2Fstable%2F.exe+download](https://minikube.sigs.k8s.io/docs/start/?arch=%2Fwindows%2Fx86-64%2Fstable%2F.exe+download) 
- Pre-requsite to install minikube 
    -  2 CPUs or more
    - 2GB of free memory
    - 20GB of free disk spaceInternet connection
    - Container or virtual machine manager, such as: [﻿Docker](https://minikube.sigs.k8s.io/docs/drivers/docker/)  , [﻿QEMU](https://minikube.sigs.k8s.io/docs/drivers/qemu/)  , [﻿Hyperkit](https://minikube.sigs.k8s.io/docs/drivers/hyperkit/)  , [﻿Hyper-V](https://minikube.sigs.k8s.io/docs/drivers/hyperv/)  , [﻿KVM](https://minikube.sigs.k8s.io/docs/drivers/kvm2/)  , [﻿Parallels](https://minikube.sigs.k8s.io/docs/drivers/parallels/)  , [﻿Podman](https://minikube.sigs.k8s.io/docs/drivers/podman/)  , [﻿VirtualBox](https://minikube.sigs.k8s.io/docs/drivers/virtualbox/)  , or [﻿VMware Fusion/Workstation](https://minikube.sigs.k8s.io/docs/drivers/vmware/)  


```
sudo apt update
```
---

### Install Docker (pre-requisite  , Container or virtual machine manager)
```
sudo apt install -y docker.io
```
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/OUhRoTW08weoJd9H3ngk0.png?ixlib=js-3.7.0 "image.png")

- Start and enable Docker.
- Add current user to docker group (To use docker without root)
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/p_ro2zz__JDQfVOOeb4yz.png?ixlib=js-3.7.0 "image.png")

- Now, logout (use `exit`  command) and connect again.
---

### Install Minikube
- To install the latest minikube **stable** release on **x86-64** **Linux** using **Debian package**:
- First, download the Minikube binary using `curl` 
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
```
```
sudo dpkg -i minikube_latest_amd64.deb
```
- This command does the following:

curl → A command-line tool to download files from the internet.
-L → Follows redirects (if the URL redirects to another link).
-O → Saves the downloaded file with the same name as in the URL.
URL → https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb is the official Minikube package for Linux (amd64 architecture).
The downloaded file will be saved as minikube_latest_amd64.deb in the current directory.


- Make it executable and move it into your path:
```
chmod +x minikube
sudo mv minikube /usr/local/bin/
```
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/S0SZlthTirlLBZS8taCWn.png?ixlib=js-3.7.0 "image.png")

---

### Install kubectl
- Download kubectl, which is a Kubernetes command-line tool.
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/UBaJgDhICDQ8Ka_tUOypX.png?ixlib=js-3.7.0 "image.png")

- Make it executable and move it into your path:
```
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
```
---

### Start Minikube
- Now, you can start Minikube with the following command:
- This command will start a single-node Kubernetes cluster inside a Docker container.
```
minikube start --driver=docker --vm=true
```
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/WLalPXBd7tQsA4T6XLBNp.png?ixlib=js-3.7.0 "image.png")

- check cluster status
```
minikube status
```
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/fe5Pvwj7-Wf1MmcM1Ct-o.png?ixlib=js-3.7.0 "image.png")



- use kubectl to interact with cluster
```
kubectl get nodes
```
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/qDlBY8SvrPkwZ1hsOzRph.png?ixlib=js-3.7.0 "image.png")

- Stop minikube
```
minikube stop
```
- Delete Minikube cluster.
```
minikube delete
```


