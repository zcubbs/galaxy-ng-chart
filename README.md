# Galaxy NG Helm Chart

### Package chart
```bash
helm package ./charts/galaxy-ng -d ./docs/releases
helm repo index ./docs --url https://zcubbs.github.io/galaxy-ng-chart
```
### Add Helm repo
```bash
helm repo add galaxy-ng https://zcubbs.github.io/galaxy-ng-chart
```

### Install

```bash
helm upgrade --install galaxy-ng galaxy-ng/galaxy-ng -n galaxy-ng --create-namespace -f values.yaml
```

### Values Example
```yaml
persistence:
  enabled: true
  storageClass: ""
  size: 2Gi

settings: |-
  CONTENT_ORIGIN='<MY_GALAXY_DOMAIN>'
  ANSIBLE_API_HOSTNAME='<MY_GALAXY_DOMAIN>'
  ANSIBLE_CONTENT_HOSTNAME='<MY_GALAXY_DOMAIN>'
  TOKEN_AUTH_DISABLED=True
```
