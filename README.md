# Infrastructure Repository

This repository contains the core infrastructure components for my Kubernetes cluster running on Talos Linux. It defines and manages fundamental cluster services including storage, networking, secrets management, and ingress capabilities.

## Components Overview

- **Networking**: [Cilium](https://cilium.io/) for networking and load balancing
- **Storage**: [Rook-Ceph](https://rook.io/) for distributed storage
- **Certificate Management**: [cert-manager](https://cert-manager.io/) with Cloudflare integration
- **Secrets Management**: [SOPS Secret Operator](https://github.com/isindir/sops-secrets-operator) and Mozilla SOPS with AGE encryption
- **Ingress**: [Traefik](https://traefik.io/) ingress controller
- **GitOps**: [ArgoCD](https://argo-cd.readthedocs.io/en/stable/) for deployment automation

## Repository Structure

```
├── .taskfiles/                 # Custom Taskfile scripts modules
├── apps/                       # Core application configurations
├── argocd/                     # ArgoCD definitions
│   ├── app-of-apps.yaml
│   ├── applications/
│   └── projects/
├── bootstrap/                  # Cluster bootstrapping configs
│   └── talos/
│       ├── talconfig.yaml
│       ├── clusterconfig/
│       └── patches/
├── .envrc                      # Direnv environment variables
├── .gitattributes              # Git attributes configuration
├── .gitignore                  # Git ignore rules
├── .pre-commit-config.yaml     # Pre-commit hooks configuration
├── .sops.yaml                  # SOPS encryption configuration
├── gitleaks.toml               # Gitleaks secret scanning configuration
├── renovate.json               # Renovate dependency management
├── taskfile.yaml               # Task runner definitions
└── yamlfmt.yaml                # YAML formatting configuration
```

## Tools & Technologies

### Core Technologies

- **[Talos Linux](https://www.talos.dev/)**: Secure, immutable Linux distribution for Kubernetes
- **[Kubernetes](https://kubernetes.io/)**: Container orchestration platform
- **[ArgoCD](https://argo-cd.readthedocs.io/en/stable/)**: Declarative GitOps continuous delivery tool

### Development & Operations Tools

- **[Taskfile](https://taskfile.dev/)**: Task runner / build tool alternative to Make
- **[SOPS](https://github.com/mozilla/sops)** with **[AGE](https://github.com/FiloSottile/age)**: Secrets encryption
- **[Pre-commit](https://pre-commit.com/)**: Git hooks for code quality and validation
- **[Renovate](https://github.com/renovatebot/renovate)**: Automated dependency updates
