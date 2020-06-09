# Kryptonetes Helm Chart Repository

This is a registry of my [helm](https://helm.sh/) charts.

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

### [geth](./charts/geth)

[Geth](https://geth.ethereum.org/) node helm chart.

### [prysm](./charts/prysm)

[Prysm](https://prylabs.network/) Beacon Chain node.

### [smartnode](./charts/smartnode)

[Rocket Pool](https://www.rocketpool.net/)'s [Smart Node](https://github.com/rocket-pool/smartnode).

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
