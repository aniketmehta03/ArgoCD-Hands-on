# ArgoCD Learning and Hands-On Practice

## Overview
This repository documents comprehensive hands-on learning and practice with **ArgoCD**, a declarative continuous delivery tool for Kubernetes. It covers all major approaches and patterns for deploying and managing applications using GitOps principles.

## What I've Learned and Practiced

### 1. **App of Apps Pattern** (`app_of_apps/`)
- Master application that manages multiple child applications
- Hierarchical application structure
- Centralized management of interdependent services
- **Applications covered:**
  - Apache
  - Nginx
  - Online Shop

### 2. **ApplicationSets** (`applicationsets/`)
- Template-based application generation
- Parameterized deployments across multiple clusters
- Dynamic application provisioning
- **Example:** Chai-app deployment with secrets and services

### 3. **CLI Approach** (`cli_approach/`)
- ArgoCD command-line operations
- Direct CLI-based application management
- Programmatic deployment control
- **Example:** Apache deployment via CLI

### 4. **Declarative Approach** (`declarative_approach/`)
- Full declarative configuration using YAML
- GitOps-native deployment methodology
- Infrastructure as Code best practices
- **Example:** Online Shop application with deployment manifests

### 5. **Git Generator** (`git_generator/`)
- Dynamic application discovery from Git repositories
- Automated sync with Git directory structures
- Multi-environment deployments
- **Covered services:**
  - Apache
  - Chai-app
  - Online Shop

### 6. **Image Updater** (`image_updater/`)
- Automated container image updates
- Kustomization-based deployments
- Continuous image synchronization
- **Example:** Chai-app with auto image updates

### 7. **Monitoring** (`monitoring/`)
- Application health monitoring and metrics
- Service observability with ArgoCD
- **Applications monitored:**
  - Chai-app
  - Online Shop

### 8. **Multi-Cluster Management** (`multicluster/`)
- Cross-cluster application deployment
- Multi-cluster synchronization
- Distributed application management
- **Example:** Online Shop across multiple clusters

### 9. **UI Approach** (`ui_approach/`)
- ArgoCD Web UI-based operations
- Visual application management
- Dashboard-driven deployments
- **Example:** Nginx deployment via UI

## Key Concepts Mastered

✅ **GitOps Principles** - Everything defined as code in Git  
✅ **Declarative Configuration** - YAML-based application definitions  
✅ **Automatic Synchronization** - Continuous reconciliation with Git source  
✅ **Multi-Cluster Deployments** - Managing applications across environments  
✅ **Application Lifecycle Management** - From creation to updates and monitoring  
✅ **Kustomization** - Template management and customization  
✅ **Secrets Management** - Secure configuration handling  
✅ **Service Deployment** - Complete application stacks with services and deployments  

## Getting Started

Refer to [argocd-demos/README.md](argocd-demos/README.md) for detailed instructions on each approach and setup guides.

For installation and prerequisites, see [Setup_installation/installation.md](Setup_installation/installation.md).

## Repository Structure

```
gitopsl/
├── argocd-demos/          # All ArgoCD demonstration patterns
├── Setup_installation/    # Installation and setup instructions
└── README.md             # This file
```

## Conclusion

This repository represents a complete hands-on learning journey with ArgoCD, covering all major deployment approaches, patterns, and best practices for Kubernetes application management using GitOps principles.
