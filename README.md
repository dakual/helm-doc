### Install Helm
```sh
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
```

```sh
helm version
```

### Create a Helm Chart
```sh
helm create myapp
helm package myapp
helm repo index .
```

### Helm add repo and search
```sh
helm repo list
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
helm repo remove bitnami
helm search repo bitnami
helm search repo nginx
helm search hub nginx
```

### There are five different ways you can express the chart you want to install
```sh
helm install myapp bitnami/nginx  # By chart reference
helm install myapp ./nginx-1.2.3.tgz  # By path to a packaged chart
helm install myapp ./nginx  # By path to an unpacked chart directory
helm install myapp https://example.com/charts/nginx-1.2.3.tgz # By absolute URL
helm install --repo https://example.com/charts/ myapp nginx # By chart reference and repo url
```

### Uninstalling a Release
```sh
helm uninstall myapp
```

### Useful commands
```sh
helm template . # Verify to template
helm lint # tests to verify that the chart is well-formed 
helm list # to list down the deployed or failed releases
helm list --all
helm status myapp # To keep track of a release's state
helm show values myapp # To see what options are configurable on a chart
helm rollback myapp 1 # roll back to a previous release
```