# Ejemplo de ArgoCD

## Actualizacion para ArgoCD

1. Ejecutar

    ```bash
    # carga de variables
    . env.sh

    # generacion de nuevo despliegue
    envsubst < example/.devops/kustomize/overlays/dev/kustomization-template.yaml > example/.devops/kustomize/overlays/dev/kustomization.yaml
    ```

2. Revisar el archivo *overlays/dev/kustomization.yaml*

## Docs

* <https://github.com/argoproj/argo-cd/blob/master/docs/operator-manual/project.yaml>

## Estructura en argo

```bash
projects - apps
# ARGOCD
|- argocd-desa
    |- argocd-desa (despliega desa-apps y desa-3scale)
|- argocd-test
    |- argocd-test (despliega test-apps y test-3scale)
# Ambiente de DESA
|- desa-apps
    |- api-sso-desa-app (apunta al codigo usando kustomize)
    |- orgullo-rojo-desa-app (apunta al codigo usando kustomize)
|- desa-3scale
    |- api-sso-desa-3scale (apunta al codigo solo 3scale)
    |- orgullo-rojo-desa-3scale (apunta al codigo solo 3scale)
# Ambiente de TEST    
|- test-apps
    |- api-sso-test-apps
    |- orgullo-rojo-test-apps
|- test-3scale
    |- api-sso-test-3scale
    |- orgullo-rojo-test-3scale
...
```
