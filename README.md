[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/skillrepos/prom-start-v2)


# Getting Started with Prometheus - lab setup

These instructions will guide you through configuring a GitHub Codespaces environment that you can use to run the course labs.

These steps **must** be completed prior to starting the actual labs.

## Create your own repository for these labs

- Ensure that you have created a repository by forking the [skillrepos/prom-start-v2](https://github.com/skillrepos/prom-start-v2) project as a template into your own GitHub area.
- You do this by clicking the `Fork` button in the upper right portion of the main project page and following the steps to create a copy in **your-github-userid/prom-start-v2** .

![Forking repository](./images/promstart1.png?raw=true "Forking the repository")

![Forking repository](./images/promstart2.png?raw=true "Forking the repository")

## Configure your codespace

1. In your forked repository, start a new codespace.

    - Click the `Code` button on your repository's landing page.
    - Click the `Codespaces` tab.
    - Click `Create codespaces on main` to create the codespace.
    - After the codespace has initialized there will be a terminal present.

![Starting codespace](./images/promstart3.png?raw=true "Starting your codespace")


## Start the Kubernetes cluster and install the apps needed
2. There is a script file in [**extra/install-apps.sh**](./roar-k8s/install-apps.sh) :

    - Run the following commands in the codespace's terminal (**This will several minutes to run and you can ignore any WARNING messages or Error from server (NotFound) messages - these are expected.**):

      ```
      extra/install-apps.sh
      ```

    - The output should look similar to the following.

```console
...Removing any old minikube instances
🙄  "minikube" profile does not exist, trying anyways.
❌  Failed to stop ssh-agent process: failed loading config: cluster "minikube" does not exist
💀  Removed all traces of the "minikube" cluster.
...Starting minikube
😄  minikube v1.32.0 on Ubuntu 20.04 (docker/amd64)
✨  Automatically selected the docker driver. Other choices: none, ssh
📌  Using Docker driver with root privileges
👍  Starting control plane node minikube in cluster minikube
🚜  Pulling base image ...
💾  Downloading Kubernetes v1.28.3 preload ...
    > preloaded-images-k8s-v18-v1...:  403.35 MiB / 403.35 MiB  100.00% 247.85 
    > gcr.io/k8s-minikube/kicbase...:  453.90 MiB / 453.90 MiB  100.00% 128.30 
🔥  Creating docker container (CPUs=2, Memory=3900MB) ...
🐳  Preparing Kubernetes v1.28.3 on Docker 24.0.7 ...
    ▪ Generating certificates and keys ...
    ▪ Booting up control plane ...
    ▪ Configuring RBAC rules ...
🔗  Configuring bridge CNI (Container Networking Interface) ...
    ▪ Using image gcr.io/k8s-minikube/storage-provisioner:v5
🔎  Verifying Kubernetes components...
🌟  Enabled addons: storage-provisioner, default-storageclass
🏄  Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default
...Creating namespace
namespace/monitoring created
"prometheus-community" has been added to your repositories
"grafana" has been added to your repositories
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "grafana" chart repository
...Successfully got an update from the "prometheus-community" chart repository
Update Complete. ⎈Happy Helming!⎈
NAME: prom-start
LAST DEPLOYED: Sun Feb 25 13:17:21 2024
NAMESPACE: monitoring
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
The Prometheus server can be accessed via port 80 on the following DNS name from within your cluster:
prom-start-prometheus-server.monitoring.svc.cluster.local

...

waiting for pod
waiting for pod
waiting for pod
waiting for pod
pod/grafana-64cbf9d66c-rb2cr condition met
pod/prom-start-alertmanager-0 condition met
pod/prom-start-kube-state-metrics-7674f66fbc-zp5vb condition met
pod/prom-start-prometheus-node-exporter-266w6 condition met
pod/prom-start-prometheus-pushgateway-cdbb5d89c-gmw48 condition met
pod/prom-start-prometheus-server-9465bbd9f-b6qkg condition met
pod/prom-start-alertmanager-0 labeled
pod/prom-start-alertmanager-0 labeled
...Forwarding ports
```

## Labs

After the codespace has started, open the labs document by going to the file tree on the left, find the file named **labs.md**, right-click on it, and open it with the **Preview** option.)

![Labs doc preview in codespace](./images/promstart58.png?raw=true "Labs doc preview in codespace")

This will open it up in a tab above your terminal. Then you can follow along with the steps in the labs. 
Any command in the gray boxes is either code intended to be run in the console or code to be updated in a file.

Labs doc: [Getting Started with Prometheus Labs](labs.md)
