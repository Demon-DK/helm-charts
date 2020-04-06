# Kubernetes Helm charts by @demon

This is a [Helm](https://helm.sh) charts repository for Kubernetes made by @demon.

### Add Helm repository

To install the repo just run:

```bash
helm repo add demon https://demon-dk.github.io/helm-charts
helm repo update
```

### Helm Charts

* **Database Adminer** 
  > [chart information](https://github.com/Demon-DK/helm-charts/blob/gh-pages/adminer/README.md)

  ```bash
  helm install --generate-name demon/adminer 
  or
  helm install [your-release-name] demon/adminer
  ```


### License
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](/LICENSE)
