# repo-gitops

Fuente de verdad del estado desplegado. Argo CD observa la rama `main`.

```
apps/
└── gestion-acueductos-api/
    ├── namespace.yaml
    ├── deployment.yaml
    ├── service.yaml
    └── argocd-application.yaml   # definición de la app en Argo CD (excluida de la sincronización)
```

Para cambiar el despliegue: edita el manifiesto, haz commit y push a `main`.
No uses `kubectl apply` ni `kubectl edit` sobre estos recursos: Argo CD revierte
cualquier diferencia con Git (`selfHeal: true`).
