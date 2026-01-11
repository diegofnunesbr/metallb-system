# MetalLB

Este guia descreve a instalação e remoção do **MetalLB** em um cluster Kubernetes, utilizando o manifesto `metallb-system.yaml`.

## Pré-requisitos

- `Kubernetes` instalado
- `kubectl` instalado
- `Argo CD` instalado
- Interface de rede `eth0` existente nos nodes onde os anúncios L2 ocorrerão
- Range de IPs `192.168.1.3–192.168.1.10` disponíveis na rede

---

## Instalar o MetalLB

```bash
git clone https://github.com/diegofnunesbr/metallb-system.git
kubectl apply -f metallb-system/applications/argocd-metallb-system.yaml
```

## Remover o MetalLB

```bash
kubectl delete -f metallb-system/applications/argocd-metallb-system.yaml
kubectl delete namespace metallb-system
```
