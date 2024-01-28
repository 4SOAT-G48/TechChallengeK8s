# Tech Challenge Infra Architecture

Atualmente esse repositorio possui esta estrutura:

```
food-delivery
├── config
│   ├── database-api-secrets.yaml
│   └── main-api-configmap.yaml
├── deployment
│   ├── database-api-deployment.yaml
│   └── main-api-deployment.yaml
├── horizontal-pod-autoscaler
│   └── main-api-hpa.yaml
├── persistent-volume
│   └── postgres-pv.yaml
├── persistent-volume-claim
│   └── postgres-pvc.yaml
└── service
    ├── main-api-service.yaml
    └── postgres-service.yaml
```

### Pre Requisitos
- Ambiente em nuvem: Minikube, Docker kubernetes, AKS, EKS, GKE
- Kubernetes: [clique aqui para documentacao oficial](https://kubernetes.io/docs/home/)
  - kubectl e kubectx

### Como inicializar este projeto?
O projeto foi executado com a nuvem **Minikube**. 
> Para fazer a instalacao do mesmo, siga o passo a passo na documentacao oficial aqui:
[Minikube](https://minikube.sigs.k8s.io/docs/start/)

**Garanta que voce esteja na pasta raiz deste projeto.**

1. Com o Minikube e Kubernetes instalado inicie o Minikube com este comando:
```sh
minikube start
```

2. Apos isso, voce ja pode inicializar o kubernetes localmente, para isso e necessario seguir uma determinada ordem:
    1. Inicialize a pasta de configuracao com o seguinte comando:
   ```sh
    kubectl apply -f food-delivery/config
   ```
    2. Inicialize a pasta de persistent volume com o seguinte comando:
   ```sh
    kubectl apply -f food-delivery/persistent-volume
   ```
    3. Inicialize a pasta de persistent volume claim com o seguinte comando:
   ```sh
    kubectl apply -f food-delivery/persistent-volume-claim
   ```
    4. Inicialize a pasta de deployment com o seguinte comando:
   ```sh
    kubectl apply -f food-delivery/deployment
   ```
    5. Inicialize a pasta de HPA com o seguinte comando:
   ```sh
    kubectl apply -f food-delivery/horizontal-pod-autoscaler
   ```
    6. Inicialize a pasta de service com o seguinte comando:
   ```sh
    kubectl apply -f food-delivery/service
   ```

3. Pronto, sua aplicacao em Kubernetes esta devidamente ativa.