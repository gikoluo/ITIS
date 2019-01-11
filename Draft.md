# Install minikube
curl -Lo minikube http://kubernetes.oss-cn-hangzhou.aliyuncs.com/minikube/releases/v0.28.1/minikube-darwin-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/

# Run minikube
minikube start

# modify DNS
minikube ssh

sudo rm /etc/resolv.conf && sudo cat > /etc/resolv.conf <<EOF
nameserver 223.5.5.5
nameserver 223.6.6.6
EOF

nameserver 114.114.114.114
nameserver 114.114.115.115

/etc/systemd/system/kubelet.service.d/10-kubeadm.conf
--pod-infra-container-image=registry.cn-hangzhou.aliyuncs.com/google-containers/pause-amd64:3.1



https://www.jianshu.com/p/02bdf2b9457f?utm_source=oschina-app


docker pull registry.cn-hangzhou.aliyuncs.com/dck8s/pause:3.1
docker tag registry.cn-hangzhou.aliyuncs.com/dck8s/pause:3.1 k8s.gcr.io/pause-amd64:3.1



systemctl stop kubelet
systemctl stop docker
iptables --flush
iptables -tnat --flush
systemctl start kubelet
systemctl start docker




#!/bin/bash

# sidecar
docker pull registry.cn-hangzhou.aliyuncs.com/dck8s/k8s-dns-sidecar:latest
docker tag registry.cn-hangzhou.aliyuncs.com/dck8s/k8s-dns-sidecar:latest k8s.gcr.io/k8s-dns-sidecar-amd64:1.14.5

# k8s-dns-kube-dns
docker pull registry.cn-hangzhou.aliyuncs.com/dck8s/k8s-dns-kube-dns:latest 
docker tag registry.cn-hangzhou.aliyuncs.com/dck8s/k8s-dns-kube-dns:latest k8s.gcr.io/k8s-dns-kube-dns-amd64:1.14.5

# k8s-dns-dnsmasq-nanny
docker pull registry.cn-hangzhou.aliyuncs.com/dck8s/k8s-dns-dnsmasq-nanny:latest
docker tag registry.cn-hangzhou.aliyuncs.com/dck8s/k8s-dns-dnsmasq-nanny:latest k8s.gcr.io/k8s-dns-dnsmasq-nanny-amd64:1.14.5

# kube-addon-manager
docker pull registry.cn-hangzhou.aliyuncs.com/dck8s/kube-addon-manager:latest
docker tag registry.cn-hangzhou.aliyuncs.com/dck8s/kube-addon-manager:latest gcr.io/google-containers/kube-addon-manager:v6.5

# kubernetes-dashboard
docker pull registry.cn-hangzhou.aliyuncs.com/dck8s/kubernetes-dashboard:latest
docker tag registry.cn-hangzhou.aliyuncs.com/dck8s/kubernetes-dashboard:latest k8s.gcr.io/kubernetes-dashboard-amd64:v1.8.1

docker pull registry.cn-hangzhou.aliyuncs.com/dck8s/pause:3.1
docker tag registry.cn-hangzhou.aliyuncs.com/dck8s/pause:3.1 k8s.gcr.io/pause-amd64:3.1



docker pull registry.cn-hangzhou.aliyuncs.com/dck8s/storage-provisioner:latest
docker tag registry.cn-hangzhou.aliyuncs.com/dck8s/storage-provisioner:latest gcr.io/k8s-minikube/storage-provisioner:v1.8.1

作者：cheneydc
链接：https://www.jianshu.com/p/02bdf2b9457f
來源：简书
简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。
