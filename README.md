# machinist

![logo](logo.svg)

Declarative Configuration for Kubernetes

## Ressources

### File

```yaml
apiVersion: machinist.barpilot.io/v1alpha1
kind: File
metadata:
  name: docker-daemon
spec:
  inline: |
    {
      "registry-mirrors": ["https://<my-docker-mirror-host>"]
    }
  path: /etc/docker/daemon.json
  mode: 644
  owner: root
  group: root
  nodeSelector:
    beta.kubernetes.io/os: linux
```

### Service

```yaml
apiVersion: machinist.barpilot.io/v1alpha1
kind: Service
metadata:
  name: docker
spec:
  enable: true
  name: docker
  nodeSelector:
    beta.kubernetes.io/os: linux
```
