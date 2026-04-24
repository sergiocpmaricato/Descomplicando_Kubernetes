# 📚 Index Formatted - Descomplicando Kubernetes

## 📄 Overview
Comprehensive study materials covering Kubernetes concepts, deployments, services, storage, probes, and cluster setup across Days 1-7.

---

## 🗂️ Day 1: Kubernetes Fundamentals

### 📄 `day-1/kind/Day-1.md`
**Topics:**
- Container Engine & Container Runtime concepts
- OCI (Open Container Initiative) and runc
- Kubernetes architecture (Control Plane, Workers, API Server, etcd, Scheduler, Controller Manager)
- Kubelet and Kube-proxy
- Port requirements (Control Plane: 6443, 2379-2380; Workers: 10250, 30000-32767)
- Pod, Deployment, ReplicaSet, Service concepts
- kubectl installation and customization (auto-complete, aliases)
- Minikube and Kind installation/usage
- Creating clusters (single-node and multi-node)
- First pod deployment and service exposure

---

## 🗂️ Day 4: Deployments, DaemonSets, and Probes

### 📄 `day-4/o que iremos ver hoje.md`
**Topics:**
- ReplicaSets and DaemonSets
- Readiness, Liveness, and Startup Probes

### 📄 `day-4/replicaset.md`
**Topics:**
- ReplicaSet role in Deployment
- ReplicaSet manages Pod replicas
- Rollback using old ReplicaSets

### 📄 `day-4/o deployment e o replicaset.md`
**Topics:**
- Deployment creates ReplicaSet
- Scaling deployments (kubectl scale vs edit YAML)
- Version updates and rollout
- Rollback with `kubectl rollout undo`

### 📄 `day-4/criando o nosso replicaset.md`
**Topics:**
- Manual ReplicaSet creation
- ReplicaSet doesn't manage versions (use Deployment instead)
- Updating images in ReplicaSet

### 📄 `day-4/daemonset.md`
**Topics:**
- DaemonSet ensures Pods run on all nodes
- Use cases: monitoring agents, network proxies, security agents
- Scales with node additions

### 📄 `day-4/criando um daemonset.md`
**Topics:**
- Node Exporter DaemonSet example
- hostNetwork, hostPath volumes
- Monitoring all nodes

### 📄 `day-4/as probles do kubernetes.md`
**Topics:**
- Three probe types: Liveness, Readiness, Startup
- Ensuring Pods are healthy and ready

### 📄 `day-4/liveness probe.md`
**Topics:**
- LivenessProbe: container health verification
- Types: tcpSocket, httpGet, exec
- Restarts Pod on failure
- Example with failing endpoint (/giropops)

### 📄 `day-4/readiness probe.md`
**Topics:**
- ReadinessProbe: traffic acceptance verification
- Removes Pod from Service endpoints on failure
- Example with path changes

### 📄 `day-4/startup probe.md`
**Topics:**
- StartupProbe: initial container startup verification
- Runs once at startup
- Prevents premature liveness/readiness checks
- Limitations: successThreshold and failureThreshold must be 1

### 📄 `day-4/exemplo com todas as probes.md`
**Topics:**
- Combined example using all three probes
- Liveness (exec), Readiness (httpGet), Startup (tcpSocket)

---

## 🗂️ Day 5: Cluster Setup and Node Management

### 📄 `day-5/o que é um cluster kubernetes.md`
**Topics:**
- Control Plane (API Server, etcd, Scheduler, Controller Manager)
- Worker nodes (Kubelet, Kube-proxy)
- Pod orchestration

### 📄 `day-5/formas de instalar o kubernetes.md`
**Topics:**
- kubeadm, Kubespray, Cloud Providers
- Managed services (EKS, GKE, AKS)
- Kops, Minikube, Kind

### 📄 `day-5/configurando portas.md`
**Topics:**
- Required ports: TCP 6443, 10250-10255, 30000-32767, 2379-2380
- Weave Net: TCP 6783, UDP 6783/6784

### 📄 `day-5/configurando os nossos nodes.md`
**Topics:**
- Disable swap
- Load kernel modules (overlay, br_netfilter)
- sysctl configuration
- Install kubeadm, kubelet, kubectl

### 📄 `day-5/instalando o containerd.md`
**Topics:**
- Install and configure containerd
- SystemdCgroup = true
- Enable kubelet service

### 📄 `day-5/adicionando outros nodes e o que é cni.md`
**Topics:**
- kubeadm join process
- CNI (Container Network Interface)
- Weave Net, Calico, Flannel, Cilium, Kube-router

### 📄 `day-5/inicializindo o cluster.md`
**File not found**

### 📄 `day-5/visualizando detalhes dos nodes.md`
**Topics:**
- kubectl describe node
- Resource allocation and usage
- Pod distribution across nodes

---

## 🗂️ Day 6: Storage (PV, PVC, StorageClass)

### 📄 `day-6/o que são volumes.md`
**Topics:**
- Ephemeral volumes (emptyDir)
- Persistent volumes
- Data persistence across Pod restarts

### 📄 `day-6/pv - persistentvolume.md`
**Topics:**
- PV types: hostPath, NFS, iSCSI, CephFS, CSI, local, fc
- Capacity, accessModes (RWO, ROX, RWX)
- Reclaim policies: Retain, Recycle, Delete
- StorageClass configuration

### 📄 `day-6/pv - persistentvolume com nfs.md`
**Topics:**
- NFS server setup
- StorageClass with no-provisioner
- Manual PV creation with NFS backend

### 📄 `day-6/storageclass.md`
**Topics:**
- Dynamic provisioning with StorageClasses
- Provisioners: AWS EBS, Azure Disk, GCE PD, local-path
- Default StorageClass configuration
- Custom StorageClass example (giropops)

---

## 🗂️ Day 7: StatefulSets and Services

### 📄 `day-7/o que é um statefulset.md`
**Topics:**
- StatefulSet for stateful applications
- Stable network identity and storage
- Ordered deployment and scaling
- Headless Service integration
- DNS naming: pod-name.service.namespace.svc.cluster.local

### 📄 `day-7/Criando um StatefulSet.md`
**Topics:**
- StatefulSet YAML structure
- serviceName field
- volumeClaimTemplates for per-Pod storage
- Ordered Pod creation (nginx-0, nginx-1, nginx-2)

### 📄 `day-7/criando o nosso headless service.md`
**Topics:**
- Headless Service (clusterIP: None)
- Direct Pod IP resolution via DNS
- nslookup for Pod discovery

### 📄 `day-7/removendo o nosso statefulset.md`
**Topics:**
- Delete StatefulSet, Headless Service, PVCs

### 📄 `day-7/criando um service.md`
**Topics:**
- Service types: ClusterIP, NodePort, LoadBalancer, ExternalName
- kubectl expose command
- YAML Service definitions
- Selectors and endpoints
- Cross-Service exposure patterns

### 📄 `day-7/services.md`
**Topics:**
- Service abstraction for Pod access
- Label selectors
- Endpoints objects
- Service types overview

---

## 📄 `README.md`
**Repository root - minimal content**

---

## 🌟 Key Features
- **100% coverage** of Days 1-7 materials
- **39 markdown files** processed
- **Structured by day** and topic
- **Practical examples** throughout
- **Production-ready patterns** highlighted