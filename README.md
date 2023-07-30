# wordpress-app
Stateful word press 


**#Pre-requisites**
1. NFS server need to be configured
2. External NFS provisioner need to be installed in K8s:
   
   **Commands:**

      helm repo add nfs-subdir-external-provisioner https://kubernetes-sigs.github.io/nfs-subdir-external-provisioner/
      helm install nfs-subdir-external-provisioner nfs-subdir-external-provisioner/nfs-subdir-external-provisioner \
       --set nfs.server=server-ip \
       --set nfs.path=path
4. Nginx ingress controller:
   
   **Commands:**

      kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/baremetal/deploy.yaml

**#Installation**

      helm install wordpressv1 wordpress
