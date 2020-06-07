# Kryptonetes Helm Chart Repository

This is an registry of my [helm](https://helm.sh/) charts.

## Prerequisites
* [Helm](https://helm.sh/) 3+

## Setup

Add the k helm repo:
```
helm repo add k https://k.github.io/helm-charts
helm repo update
```

Then configure a values.yaml for the chart you want to install.

## List of Charts

### [smartnode](./charts/smartnode)

[Rocket Pool](https://www.rocketpool.net/)'s [Smart Node](https://github.com/rocket-pool/smartnode) in Kubernetes.

## Deploy to Github Pages

Deploy requires [`cr`](https://github.com/helm/chart-releaser) tool 

### Enable Github Pages (only first time)

Settings > Options > Github Pages > Source > Select master branch

### Package chart

```
helm package charts/<chart-to-package> --destination .deploy
```

### Upload New Release

```
cr upload --config config.yaml --token <github-deploy-token>
```

### Generate new index
```
cr index --config config.yaml
git add index.yaml
git commit -m "Update index.yaml"
git push
```
