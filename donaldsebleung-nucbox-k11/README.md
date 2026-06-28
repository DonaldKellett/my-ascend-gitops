## NucBox K11 MiniPC with OrangePi AI Studio Pro

Argo CD GitOps manifests for my single-node K3s cluster with the following hardware specifications.

1. x86 PC: [GMKtec NucBox K11 Mini PC](https://www.gmktec.com/products/amd-ryzen%E2%84%A2-9-8945hs-nucbox-k11)
1. Huawei Ascend NPU: [OrangePi AI Studio Pro](http://www.orangepi.cn/html/hardWare/computerAndMicrocontrollers/details/Orange-Pi-AI-Studio-Pro.html)

| Resource | Specifications |
| --- | --- |
| vCPU | 16 |
| Memory | 96G |
| Storage | 1T |
| NPU | Ascend 310P1 x2 |
| AI computing capability | 352 TOPS / 176 TFLOPS |
| Total device memory | 192G |

### Quickstart

```bash
kubectl kustomize platform/overlays/prod/ | \
    kubectl -n argocd apply -f -
```

### Components

The platform components installed are listed in the table below.

| Component | Function |
| --- | --- |
| [Argo CD](https://argo-cd.readthedocs.io/en/stable/) | GitOps reconciliation |
| [system-upgrade-controller](https://github.com/rancher/system-upgrade-controller) | K3s upgrade |
| [Sealed Secrets](https://github.com/bitnami/sealed-secrets) | Secrets management |
| [cert-manager](https://cert-manager.io/) | TLS certificates |
| [ExternalDNS](https://kubernetes-sigs.github.io/external-dns/v0.21.0/) | DNS management |
| [JupyterHub](https://jupyterhub.readthedocs.io/en/stable/) | Notebook self-service |
