## Deployment projeto conversão de temperatura em kubernetes


## Requisitos - Ter instalado os seguintes serviços.

- Kubectl - https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
- K3d - https://k3d.io/v5.4.1/
- Docker - https://docs.docker.com/engine/install/ubuntu/

## Como iniciar com esse projeto

Download do projeto.

```bash
git clone https://github.com/mvcardim/kubernetes-conversao-temp.git
```

- Iniciar um cluster.

No meu caso, estou subindo um cluster com 2 agents e 2 servers, analise se para você da certo o total de nós.
Também neste comando, estou especificando a porta da aplicação "8080", mapeando localmente uma porta "30000" para o loadbalancer, caso tenha muitos pods e seja escalável.

```bash
k3d cluster create cluster-temperatura --agents 2 --servers 2 -p "8080:30000@loadbalancer"
```

- Para realizar o deployment da aplicação, se da necessário rodar apenas um comando.

```bash
kubectl apply -f deployment.yml
```

- Você pode acompanhar os serviços com o comando.
Nele você consegue ver todos os "pods", "services", "replicateSets", "deployments" e etc.

```bash
kubectl get all
```

Saída do comando.


