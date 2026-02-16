# metallb-system

Este guia descreve a instalação e remoção do **metallb-system** em um cluster Kubernetes, utilizando o manifesto `metallb-system.yaml`.

## Pré-requisitos

- `Kubernetes` instalado
- `kubectl` instalado
- `Argo CD` instalado
- Interface de rede `eth0` existente nos nodes onde os anúncios L2 ocorrerão
- Range de IPs `192.168.1.3–192.168.1.10` disponíveis na rede

## Estrutura do repositório

```text
metallb-system/
├── applications/
│   └── argocd.metallb-system.yaml     # Application do Argo CD
├── metallb-system.yaml                # Manifests do metallb-system
└── README.md
```

---

## Instalar o metallb-system

```bash
git clone https://github.com/diegofnunesbr/metallb-system.git
cd metallb-system
kubectl apply -f applications/argocd.metallb-system.yaml
```

## Remover o metallb-system

```bash
cd metallb-system
kubectl delete -f applications/argocd.metallb-system.yaml
kubectl delete namespace metallb-system --ignore-not-found
```
