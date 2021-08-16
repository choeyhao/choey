# choey
K3S can't add an agent into the service

root@sutpc:/home/sutpc# systemctl status k3s-agent
● k3s-agent.service - Lightweight Kubernetes
   Loaded: loaded (/etc/systemd/system/k3s-agent.service; enabled; vendor preset: enabled)
   Active: active (running) since Mon 2021-08-16 16:36:13 CST; 12s ago
     Docs: https://k3s.io
  Process: 10112 ExecStartPre=/sbin/modprobe overlay (code=exited, status=0/SUCCESS)
  Process: 10094 ExecStartPre=/sbin/modprobe br_netfilter (code=exited, status=0/SUCCESS)
 Main PID: 10113 (k3s-agent)
    Tasks: 10
   CGroup: /system.slice/k3s-agent.service
           └─10113 /usr/local/bin/k3s agent

 systemd[1]: Starting Lightweight Kubernetes...
 sutpc systemd[1]: Started Lightweight Kubernetes.
 sutpc k3s[10113]: time="2021-08-16T16:36:13+08:00" level=info msg="Acquiring lock file /var/lib/rancher/k3s/data/.lock"
 sutpc k3s[10113]: time="2021-08-16T16:36:13+08:00" level=info msg="Preparing data dir /var/lib/rancher/k3s/data/d57e75cb49c3cfd88307a8669e8adcf6b7740b66d6125a45c00aaa54301a5746"
 sutpc k3s[10113]: time="2021-08-16T16:36:16.543761287+08:00" level=info msg="Starting k3s agent v1.21.3+k3s1 (1d1f220f)"
 sutpc k3s[10113]: time="2021-08-16T16:36:16.545863446+08:00" level=info msg="Running load balancer 127.0.0.1:6444 -> [192.168.180.81:6443]"

root@:/# kubectl get nodes -o wide
NAME    STATUS   ROLES                  AGE   VERSION        INTERNAL-IP      EXTERNAL-IP   OS-IMAGE             KERNEL-VERSION       CONTAINER-RUNTIME
         Ready    control-plane,master   96m   v1.21.3+k3s1   192.168.180.81   <none>        Ubuntu 18.04.1 LTS   4.15.0-151-generic   containerd://1.4.8-k3s1

