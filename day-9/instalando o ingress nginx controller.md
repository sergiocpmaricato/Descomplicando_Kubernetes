
Minikube
Para instalar o ingress controller no Minikube, você pode usar o sistema de addons do próprio Minikube. O comando a ser executado é:
minikube addons enable ingress

MicroK8s
No caso do MicroK8s, o ingress controller também pode ser instalado via sistema de addons. O comando para isso é:
microk8s enable ingress

AWS (Amazon Web Services)
Na AWS, o ingress controller é exposto através de um Network Load Balancer (NLB). O comando para instalação é:
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.2/deploy/static/provider/aws/deploy.yaml
Você também pode configurar a terminação TLS no Load Balancer da AWS, editando o arquivo deploy.yaml com as informações do seu Certificate Manager (ACM).

Azure
No Azure, o ingress controller é instalado com o comando:
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.2/deploy/static/provider/cloud/deploy.yaml

GCP (Google Cloud Platform)
No GCP, primeiramente certifique-se de que seu usuário tem permissões de cluster-admin. Depois, instale o ingress controller com:
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.2/deploy/static/provider/cloud/deploy.yaml
Você também pode precisar configurar regras de firewall se estiver usando um cluster privado.

Bare Metal
Para instalações em Bare Metal ou VMs "cruas", você pode usar um NodePort para testes rápidos:
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.2/deploy/static/provider/baremetal/deploy.yaml
Este comando mapeará o ingress controller para uma porta no intervalo de 30000-32767.

