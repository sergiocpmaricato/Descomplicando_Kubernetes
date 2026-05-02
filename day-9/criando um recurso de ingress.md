Criando um Recurso de Ingress
Agora, vamos criar um recurso de Ingress para nosso serviço giropops-senhas criado anteriormente. Crie um arquivo chamado ingress-1.yaml:

apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: giropops-senhas
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  rules:
  - http:
      paths:
      - path: /giropops-senhas
        pathType: Prefix
        backend:
          service: 
            name: giropops-senhas
            port:
              number: 5000

Após criar o arquivo, aplique-o:

kubectl apply -f ingress-1.yaml
Agora vamos ver se o nosso Ingress foi criado corretamente:

kubectl get ingress
Para ver com mais detalhes, você pode usar o comando describe:

kubectl describe ingress ingress-1
Tanto na saída do comando get quanto na saída do comando describe, você deve ver o endereço IP do seu Ingress no campo Address.

Você pode pegar esse IP através do comando:

kubectl get ingress ingress-1 -o jsonpath='{.status.loadBalancer.ingress[0].hostname}'
Caso você esteja utilizando um cluster gerenciado por algum provedor de nuvem, como o GKE, você pode utilizar o comando:

kubectl get ingress ingress-1 -o jsonpath='{.status.loadBalancer.ingress[0].ip}'
Isso porque quando você possui um cluster EKS, AKS, GCP, etc, o Ingress Controller irá criar um LoadBalancer para você, e o endereço IP do LoadBalancer será o endereço IP do seu Ingress, simples assim.

Para testar, você pode usar o comando curl com o IP, hostname ou load balancer do seu Ingress:

curl ENDEREÇO_DO_INGRESS/giropops-senhas
